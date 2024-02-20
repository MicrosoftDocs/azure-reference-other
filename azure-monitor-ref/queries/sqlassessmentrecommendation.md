---
title: Example log table queries for SQLAssessmentRecommendation
description:  Example queries for SQLAssessmentRecommendation log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the SQLAssessmentRecommendation table


### SQL Recommendations by Focus Area  


Count all SQL reccomendations by focus area.  

```query
SQLAssessmentRecommendation
| summarize AggregatedValue = count() by FocusArea
```



### SQL Recommendations by Computer  


Count SQL recommendations with failed result by computer.  

```query
SQLAssessmentRecommendation
| where RecommendationResult == "Failed"
| summarize AggregatedValue = count() by Computer
```



### SQL Recommendations by Instance  


Count SQL recommendations with failed result by instance.  

```query
SQLAssessmentRecommendation
| where RecommendationResult == "Failed"
| summarize AggregatedValue = count() by SqlInstanceName
```



### SQL Recommendations by Database  


Count SQL recommendations with failed result by database.  

```query
SQLAssessmentRecommendation
| where RecommendationResult == "Failed"
| summarize AggregatedValue = count() by DatabaseName
```



### SQL Recommendations by AffectedObjectType  


Count SQL recommendations with failed result by affected object type.  

```query
SQLAssessmentRecommendation
| where RecommendationResult == "Failed"
| summarize AggregatedValue = count() by AffectedObjectType
```



### How many times did each unique SQL Recommendation trigger?  


Count SQL recommendations with failed result by recommendation.  

```query
SQLAssessmentRecommendation
| where RecommendationResult == "Failed"
| summarize AggregatedValue = count() by Recommendation
```



### High priority SQL Assessment recommendations  


Latest high priority security recommendation with result failed by recommendation Id.  

```query
SQLAssessmentRecommendation
| where FocusArea == 'Security and Compliance' and RecommendationResult == 'Failed' and RecommendationScore>=35
| summarize arg_max(TimeGenerated, *) by RecommendationId
```

