---
title: Example log table queries for REDConnectionEvents
description:  Example queries for REDConnectionEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the REDConnectionEvents table


### Unique authenticated Redis client IP addresses  


Unique Redis client IP addresses that have successfully authenticated to the cache.  

```query
REDConnectionEvents
// https://docs.redis.com/latest/rs/security/audit-events/#status-result-codes
// EventStatus :
// 0    AUTHENTICATION_FAILED    -    Invalid username and/or password.
// 1    AUTHENTICATION_FAILED_TOO_LONG    -    Username or password are too long.
// 2    AUTHENTICATION_NOT_REQUIRED    -    Client tried to authenticate, but authentication isn’t necessary.
// 3    AUTHENTICATION_DIRECTORY_PENDING    -    Attempting to receive authentication info from the directory in async mode.
// 4    AUTHENTICATION_DIRECTORY_ERROR    -    Authentication attempt failed because there was a directory connection error.
// 5    AUTHENTICATION_SYNCER_IN_PROGRESS    -    Syncer SASL handshake. Return SASL response and wait for the next request.
// 6    AUTHENTICATION_SYNCER_FAILED    -    Syncer SASL handshake. Returned SASL response and closed the connection.
// 7    AUTHENTICATION_SYNCER_OK    -    Syncer authenticated. Returned SASL response.
// 8    AUTHENTICATION_OK    -    Client successfully authenticated.
| where EventType == "auth" and EventStatus == 2 or EventStatus == 8 or EventStatus == 7
| summarize count() by ClientIp
```



### Redis client authentication requests per hour  


Redis client authentication requests per hour within the specified IP address range. Includes both successful and unsuccessful requests.  

```query
REDConnectionEvents
| extend EventTime = unixtime_seconds_todatetime(EventEpochTime)
// For particular datetime filtering, add '| where EventTime between (StartTime .. EndTime)'
// For particular IP range filtering, add '| where ipv4_is_in_range(ClientIp, IpRange)'
// IP range can be defined like this 'let IpRange = "10.1.1.0/24";' at the top of query.
| where EventType == "auth"
| summarize AuthencationRequestsCount = count() by TimeRange = bin(EventTime, 1h)

```



### Redis client connections per hour  


Redis client connections per hour within the specified IP address range.  

```query
REDConnectionEvents
// For particular datetime filtering, add '| where EventTime between (StartTime .. EndTime)'
// For particular IP range filtering, add '| where ipv4_is_in_range(ClientIp, IpRange)'
// IP range can be defined like this 'let IpRange = "10.1.1.0/24";' at the top of query.
| extend EventTime = unixtime_seconds_todatetime(EventEpochTime)
| where EventType == "new_conn"
| summarize ConnectionCount = count() by TimeRange = bin(EventTime, 1h)

```



### Redis client disconnections per hour  


Redis client disconnections per hour within the specified IP address range.  

```query
REDConnectionEvents
// For particular datetime filtering, add '| where EventTime between (StartTime .. EndTime)'
// For particular IP range filtering, add '| where ipv4_is_in_range(ClientIp, IpRange)'
// IP range can be defined like this 'let IpRange = "10.1.1.0/24";' at the top of query.
| extend EventTime = unixtime_seconds_todatetime(EventEpochTime)
| where EventType == "close_conn"
| summarize DisconnectionCount = count() by TimeRange = bin(EventTime, 1h)

```



### Unsuccessful authentication attempts on Redis cache  


Authentication attempts on Redis cache which were unsuccessful.  

```query
REDConnectionEvents
// https://docs.redis.com/latest/rs/security/audit-events/#status-result-codes
// EventStatus : 
// 0    AUTHENTICATION_FAILED    -    Invalid username and/or password.
// 1    AUTHENTICATION_FAILED_TOO_LONG    -    Username or password are too long.
// 2    AUTHENTICATION_NOT_REQUIRED    -    Client tried to authenticate, but authentication isn’t necessary.
// 3    AUTHENTICATION_DIRECTORY_PENDING    -    Attempting to receive authentication info from the directory in async mode.
// 4    AUTHENTICATION_DIRECTORY_ERROR    -    Authentication attempt failed because there was a directory connection error.
// 5    AUTHENTICATION_SYNCER_IN_PROGRESS    -    Syncer SASL handshake. Return SASL response and wait for the next request.
// 6    AUTHENTICATION_SYNCER_FAILED    -    Syncer SASL handshake. Returned SASL response and closed the connection.
// 7    AUTHENTICATION_SYNCER_OK    -    Syncer authenticated. Returned SASL response.
// 8    AUTHENTICATION_OK    -    Client successfully authenticated.
| where EventType == "auth" and EventStatus != 2 and EventStatus != 8 and EventStatus != 7
| project ClientIp, EventStatus, ConnectionId
```

