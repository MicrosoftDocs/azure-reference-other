---
title: "@@Diagnostics (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2018-05-18"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# &#x40;&#x40;Diagnostics (U-SQL)
The U-SQL .NET extension model added a new object called `Microsoft.Analytics.Diagnostics.DiagnosticStream` that enables (limited)  recording of diagnostic information into a file in the job folder. 

The .NET user code can be written using the `DiagnosticStream` object and the actual generation of the diagnostic file can be controlled by setting the system variable `@@Diagnostics` in the U-SQL script using the user code. The default setting is off. The following script statement will turn it on:

```
SET @@Diagnostics = true;
```

## Generated File
Each job will receive its own file in the job folder in ADLS at:

`/system/jobservice/jobs/Usql/{yyyy}/{MM}/{dd}/{HH}/{mm}/{job-guid}/diagnosticstreams/diagnostic.xml`

The [Visual Studio ADL Tool](https://www.microsoft.com/en-us/download/details.aspx?id=49504) has a link to the folder containing the diagnostic stream's folder.

The file contains the following information (`...` indicates repetition) as an XML fragment in UTF-8 encoding (meaning it can have no XML declaration and can have more than one top-level XML element):

    <Vertex name="vertexname" v="vertexversion" guid="vertex-guid-withoutbraces">
      <l>entitized-user-provided-content</l> ...
    </Vertex> ...

Note that each Vertex element appears in its own line and there are no CR/LF or additional whitespaces in its content (they are added in the example above for better visualization only).

The diagnosis has the following limits:

1.	Each `entitized-user-provided-content` cannot be larger than 100kb of UTF-16 encoded, pre-entitized data (e.g., the user writes `A\rB` which will be entitized to `A&xD;B`. This will be counted as 3 bytes).
2.	The overall diagnosis file size limit is 5GB. This includes all the XML tags and attribute information.

In the case that the diagnostic information exceeds the limits above, writing the diagnosis information should not fail. Therefore, the following information will be added as an indication that the data got truncated:

1.	Each Line that is being written that ends up being too long will be represented by the following element:

        <l truncated="true">first-100kb-of-user-provided-content-in-entitizedform<l>

2.	If the file gets over 5GB in size, one special Vertex element will be appended at the end of the file of the following form:

        <Vertex truncated="true"/>

## Defaulted information
We may extend this format in the future. Therefore, there is an implied version attribute on each of the Vertex elements that is implied to be version="1.0".  Future versions will update the minor version, if backwards-compatible changes are done to the XML format; and they will update the major version, if the changes are not backwards-compatible.

## Timing of writing information to the file
In order to strike a balance between seeing the progress too late and writing too often and writing invalid XML fragments, the vertex information is written at the end of a vertex execution and reports both successful and failed vertices.

Each time the content of the file becomes visible, the file is considered to be sealed.

Handling multiple vertex executions and failed vertices:

ADLA executes a vertex possibly more than once for reasons such as:

1.	A vertex failed and the system decides that a retry may succeed.
2.	The system may decide to duplicate an execution of a vertex and pick the fastest to succeed.

Regardless of the reason, each vertex execution gets its own version number. 

A vertex may also fail due to system error or user error.

The following list indicates which vertex version’s data is being written into the diagnostic file:

1.	A vertex succeeds once: The vertex data is written with the vertex’s version number.
2.	A vertex succeeds several times (e.g., they were submitted concurrently and both succeeded): The information for both vertices is written. The vertices have different version numbers. The highest version number is the one that is taken as the input for the next stage.
3.	A retried vertex after a failed vertex: Both the retried and the failed vertex information is written. The highest version information is the one considered as the input for the next stage. The element representing the failed vertex gets an additional attribute `failed="true"`.
4.	A vertex fails due to user-error: The last failed vertex is written with the content. The element representing the failed vertex gets an additional attribute `failed="true"`.
5.	A vertex fails due to system-error: The last failed vertex is written with the content, as long as the error is catch-able (e.g., a store read error). The element representing the failed vertex gets an additional attribute `failed="true"`.
6.	A vertex fails due to a system crash: No diagnostics is written. This condition should be reported as a system issue.
7.	A vertex is discarded by the job manager before it finishes: No diagnostics is written.

> [!IMPORTANT]  
> Items 4 and 5, above, are currently not recording diagnostics. The above specification will be implemented in a future refresh.

## Diagnostic File Expiration
Since the file is written into the job folder, its expiration is subject to the job data expiration. The user can either increase the expiration for the job, or copy the file into a separate location.

_Methods on the `DiagnosticStream` class_

```
void DiagnosticStream.WriteLine(string user_provided_content)
```

Takes the `user_provided_content` and writes up to the first 100kb of the provided data (size determined based on UTF-16 encoding) into the diagnose stream into an `l` element after entitizing CR and LF using XML character code entities and entitizing < and & with the named XML character entities. If the data is more than 100kb an additional attribute `truncated="true"` will be added to the `l` element. Note that the data in the file will be UTF-8 encoded.

Example:

    DiagnosticStream.WriteLine("This is an example with an &");

Adds the following line to the vertex’s element content:

    <l>This is an example with an &amp;</l>

_System Variable controls Diagnostic Output_ 

Often diagnostics may only be used under certain conditions (debug executions etc) and otherwise can lead to negative performance impact, even if the user wraps it with an if statement. 

Therefore, U-SQL provides a system variable `@@Diagnostics` to control if the DiagnosticStream code gets invoked or not.

The two acceptable values are `true` and `false`. The default is `false`, which means that the DiagnosticStream code does not get invoked. The following script statement will turn it on:

```
SET @@Diagnostics = true;
```

The system variable can only be set once per script invocation. If a script contains more than one statement setting it, a compile time error is raised.


_Example:_

Given the file `/Samples/Data/SearchLogWithHeaderandWronglines.tsv` with the following content:

    id	date	market	search_string	time	found_uris	visited_uris
    399266	2/15/2012 11:53:16 AM	en-us	how to make nachos	73	www.nachos.com;www.wikipedia.com	NULL
    382045	2/15/2012 11:53:18 AM	en-gb	best ski resorts	614	skiresorts.com;ski-europe.com;www.travelersdigest.com/ski_resorts.htm	ski-europe.com;www.travelersdigest.com/ski_resorts.htm
    382045	2/16/2012 11:53:20 AM	en-gb	broken leg	74	mayoclinic.com/health;webmd.com/a-to-z-guides;mybrokenleg.com;wikipedia.com/Bone_fracture	mayoclinic.com/health;webmd.com/a-to-z-guides;mybrokenleg.com;wikipedia.com/Bone_fracture
    106479	2/16/2012 11:53:50 AM	en-ca	south park episodes	24	southparkstudios.com;wikipedia.org/wiki/Sout_Park;imdb.com/title/tt0121955;simon.com/mall	southparkstudios.com
    906441	2/16/2012 11:54:01 AM	en-us	cosmos	1213	cosmos.com;wikipedia.org/wiki/Cosmos:_A_Personal_Voyage;hulu.com/cosmos	NULL
    351530	2/16/2012 11:54:01 AM	en-fr	microsoft	241	microsoft.com;wikipedia.org/wiki/Microsoft;xbox.com	NULL
    640806	2/16/2012 11:54:02 AM	en-us	wireless headphones	502	www.amazon.com;reviews.cnet.com/wireless-headphones;store.apple.com	www.amazon.com;store.apple.com
    304305	2/16/2012 11:54:03 AM	en-us	dominos pizza	60	dominos.com;wikipedia.org/wiki/Domino's_Pizza;facebook.com/dominos	dominos.com
    460748	2/16/2012 11:54:04 AM	en-us	yelp	1270	yelp.com;apple.com/us/app/yelp;wikipedia.org/wiki/Yelp,_Inc.;facebook.com/yelp	yelp.com
    354841	2/16/2012 11:59:01 AM	en-us	how to run	610	running.about.com;ehow.com;go.com	running.about.com;ehow.com
    
    354068	2/16/2012 12:00:33 PM	en-mx	what is sql	422	wikipedia.org/wiki/SQL;sqlcourse.com/intro.html;wikipedia.org/wiki/Microsoft_SQL	wikipedia.org/wiki/SQL
    674364	2/16/2012 12:00:55 PM	en-us	mexican food redmond	283	eltoreador.com;yelp.com/c/redmond-wa/mexican;agaverest.com	NULL
    347413	2/16/2012 12:11:55 PM	en-gr	microsoft	305	microsoft.com;wikipedia.org/wiki/Microsoft;xbox.com	NULL
    848434	2/16/2012 12:12:35 PM	en-ch	facebook	10	facebook.com;facebook.com/login;wikipedia.org/wiki/Facebook	facebook.com
    604846	2/16/2012 12:13:55 PM	en-us	wikipedia	612	wikipedia.org;en.wikipedia.org;en.wikipedia.org/wiki/Wikipedia	wikipedia.org
    840614	2/16/2012 12:13:56 PM	en-us	xbox	1220	xbox.com;en.wikipedia.org/wiki/Xbox;xbox.com/xbox360	xbox.com/xbox360
    656666	2/16/2012 12:15:55 PM	en-us	hotmail	691	hotmail.com;login.live.com;msn.com;en.wikipedia.org/wiki/Hotmail	NULL
    951513	2/16/2012 12:17:00 PM	en-us	pokemon	63	pokemon.com;pokemon.com/us;serebii.net	pokemon.com
    350350	2/16/2012 12:18:17 PM	en-us	wolfram	30	wolframalpha.com;wolfram.com;mathworld.wolfram.com;en.wikipedia.org/wiki/Stephen_Wolfram	NULL
    corrupted id	2/16/2012 12:18:17 PM	en-us	wolfram	30	wolframalpha.com;wolfram.com;mathworld.wolfram.com;en.wikipedia.org/wiki/Stephen_Wolfram	NULL
    641615	2/16/2012 12:19:55 PM	en-us	kahn	119	khanacademy.org;en.wikipedia.org/wiki/Khan_(title);answers.com/topic/genghis-khan;en.wikipedia.org/wiki/Khan_(name)	khanacademy.org
    321065	2/16/2012 12:20:03 PM	en-us	clothes	732	gap.com;overstock.com;forever21.com;footballfanatics.com/college_washington_state_cougars	footballfanatics.com/college_washington_state_cougars
    651777	2/16/2012 12:20:33 PM	en-us	food recipes	183	allrecipes.com;foodnetwork.com;simplyrecipes.com	foodnetwork.com
    666352	2/16/2012 12:21:03 PM	en-us	weight loss	630	en.wikipedia.org/wiki/Weight_loss;webmd.com/diet;exercise.about.com	webmd.com/diet

and the U-SQL script

```sql
SET @@FeaturePreviews = "DIAGNOSTICS:ON";

@data =
    EXTRACT [id] int,
            [date] DateTime,
            [market] string,
            [searchstring] string,
            [time] int,
            [found_urls] string,
            [visited_urls] string
    FROM "/Samples/Data/SearchLogWithHeaderandWronglines.tsv"
    USING new USQLApplication1.MyExtractor();

OUTPUT @data
TO "/output/searchlog.tsv"
USING Outputters.Tsv(outputHeader:true, quoting: false);
```
 
with the following custom extractor (in code-behind):

```csharp
using Microsoft.Analytics.Interfaces;
using Microsoft.Analytics.Diagnostics;
using System;
using System.Collections.Generic;
using System.IO;
using System.Text;

namespace USQLApplication1
{        
    [SqlUserDefinedExtractor]
    public class MyExtractor : IExtractor
    {
        public override IEnumerable<IRow> Extract(IUnstructuredReader input, IUpdatableRow outputrow)
        {
            ulong rowId = 0;
            char column_delimiter = '\t';
            string lastLine = string.Empty;
            string line;
            foreach (var stream in input.Split(new byte[] { 0x0d, 0x0a }))
            {
                var reader = new StreamReader(stream, encoding: Encoding.UTF8);
                line = reader.ReadToEnd();

                if (string.IsNullOrEmpty(line))
                {
                    DiagnosticStream.WriteLine(String.Format("Skip empty line at line {0}.", rowId));
                }
                else if (line.StartsWith("id\t"))
                {
                    DiagnosticStream.WriteLine(String.Format("Skip header line at line {0}.", rowId));
                }
                else
                {
                    try
                    {
                        var tokens = line.Split(column_delimiter);
                        outputrow.Set<int>("id", int.Parse(tokens[0]));
                        outputrow.Set<DateTime>("date", DateTime.Parse(tokens[1]));
                        outputrow.Set<string>("market", tokens[2]);
                        outputrow.Set<string>("searchstring", tokens[3]);
                        outputrow.Set<int>("time", int.Parse(tokens[4]));
                        outputrow.Set<string>("found_urls", tokens[5]);
                        outputrow.Set<string>("visited_urls", tokens[6]);
                    }
                    catch
                    {
                        DiagnosticStream.WriteLine("============\t <afds />====\n==============\xc4");
                        DiagnosticStream.WriteLine(String.Format("Last  line {0}: {1}", rowId - 1, lastLine));
                        DiagnosticStream.WriteLine(String.Format("Error line {0}: {1}", rowId, line));
                        DiagnosticStream.WriteLine("==============================");
                    }

                    yield return outputrow.AsReadOnly();
                }

                lastLine = line;
                ++rowId;
            }
        }
    }
}
```

will produce the following file in the job folder at `/system/jobservice/jobs/Usql/yyyy/MM/dd/HH/mm/jobguid/diagnosticstreams/diagnosticstream.xml` in your account (where the `yyyy/MM/dd/HH/mm/jobguid` path identifies the job's time and GUID):

    <Vertex name="SV1_Extract[0][0]" v="0" guid="{DD9A2150-594D-45F2-8851-56DE40C2732A}" truncated="false"><l>Skip header line at line 0.</l><l>Skip empty line at line 11.</l><l>============	 &lt;afds /&gt;====&#x0a;==============Ä</l><l>Last  line 20: 350350	2/16/2012 12:18:17 PM	en-us	wolfram	30	wolframalpha.com;wolfram.com;mathworld.wolfram.com;en.wikipedia.org/wiki/Stephen_Wolfram	NULL</l><l>Error line 21: corrupted id	2/16/2012 12:18:17 PM	en-us	wolfram	30	wolframalpha.com;wolfram.com;mathworld.wolfram.com;en.wikipedia.org/wiki/Stephen_Wolfram	NULL</l><l>==============================</l></Vertex>


## See Also 
* [Built-in U-SQL System Objects and Extensions](built-in-u-sql-system-objects-and-extensions.md)
* [DECLARE Variables (U-SQL)](declare-variables-u-sql.md)
