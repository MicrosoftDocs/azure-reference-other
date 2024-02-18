---
title: Example log table queries for Syslog
description:  Example queries for Syslog log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the Syslog table


### Find Linux kernel events  


Find events reported by Linux kernel process, regarding killed processes.  

```query
// To create an alert for this query, click '+ New alert rule'
Syslog
| where ProcessName == "kernel" and SyslogMessage contains "Killed process"
```



### All Syslog  


Last 100 Syslog.  

```query
Syslog 
| top 100 by TimeGenerated desc
```



### All Syslog with errors  


Last 100 Syslog with erros.  

```query
Syslog 
| where SeverityLevel == "err" or  SeverityLevel == "error"
| top 100 by TimeGenerated desc
```



### All Syslog by facility  


All Syslog by facility.  

```query
Syslog 
| summarize count() by Facility
```



### All Syslog by process name  


All Syslog by process name.  

```query
Syslog 
| summarize count() by ProcessName
```



### Users Added to Linux Group by Computer  


Lists computers with users added to Linux group.  

```query
Syslog
| where Facility == 'authpriv' and SyslogMessage has 'to group' and (SyslogMessage has 'add' or SyslogMessage has 'added')
| summarize by Computer
```



### New Linux Group Created by Computer  


Lists computers with new Linux group created.  

```query
Syslog
| where Facility == 'authpriv' and SyslogMessage has 'new group'
| summarize count() by Computer
```



### Failed Linux User Password Change  


Lists computers wih failed Linux user password change.  

```query
Syslog
| where Facility == 'authpriv' and ((SyslogMessage has 'passwd:chauthtok' and SyslogMessage has 'authentication failure') or SyslogMessage has 'password change failed')
| summarize count() by Computer
```



### Computers With Failed Ssh Logons  


Lists computers with failed ssh logons.  

```query
Syslog
| where (Facility == 'authpriv' and SyslogMessage has 'sshd:auth' and SyslogMessage has 'authentication failure') or (Facility == 'auth' and ((SyslogMessage has 'Failed' and SyslogMessage has 'invalid user' and SyslogMessage has 'ssh2') or SyslogMessage has 'error: PAM: Authentication failure'))
| summarize count() by Computer
```



### Computers With Failed Su Logons  


Lists computers with failed su logons.  

```query
Syslog
| where (Facility == 'authpriv' and SyslogMessage has 'su:auth' and SyslogMessage has 'authentication failure') or (Facility == 'auth' and SyslogMessage has 'FAILED SU')
| summarize count() by Computer
```



### Computers With Failed Sudo Logons  


Lists computers with failed sudo logons.  

```query
Syslog
| where (Facility == 'authpriv' and SyslogMessage has 'sudo:auth' and (SyslogMessage has 'authentication failure' or SyslogMessage has 'conversation failed')) or ((Facility == 'auth' or Facility == 'authpriv') and SyslogMessage has 'user NOT in sudoers')
| summarize count() by Computer
```

