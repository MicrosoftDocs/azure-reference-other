---
title: Azure Monitor Logs reference - StorageFileLogs
description: Reference for StorageFileLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# StorageFileLogs

 Storage File Service Logs Schema

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Storage account




## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime|The Universal Time Coordinated (UTC) time when the request was received by storage.|
|AccountName|string|The name of the storage account.|
|Location|string|The location of storage account.|
|Protocol|string|The protocol that is used in the operation.|
|OperationName|string|The type of REST operation that was performed.|
|AuthenticationType|string|The type of authentication that was used to make the request.|
|StatusCode|string|The HTTP status code for the request. If the request is interrupted, this value might be set to Unknown.|
|StatusText|string|The status of the requested operation.|
|DurationMs|real|The total time, expressed in milliseconds, to perform the requested operation. This includes the time to read the incoming request, and to send the response to the requester.|
|ServerLatencyMs|real|The total time expressed in milliseconds to perform the requested operation. This value doesn't include network latency (the time to read the incoming request and send the response to the requester).|
|Uri|string|Uniform resource identifier that is requested.|
|CallerIpAddress|string|The IP address of the requester, including the port number.|
|CorrelationId|string|The ID that is used to correlate logs across resources.|
|SchemaVersion|string|The schema version of the log.|
|OperationVersion|string|The storage service version that was specified when the request was made. This is equivalent to the value of the x-ms-version header.|
|AuthenticationHash|string|The hash of authentication token.|
|RequesterObjectId|string|The OAuth object ID of the requester.|
|RequesterTenantId|string|The OAuth tenant ID of identity.|
|RequesterAppId|string|The Open Authorization (OAuth) application ID that is used as the requester.|
|RequesterAudience|string|The OAuth audience of the request.|
|RequesterTokenIssuer|string|The OAuth token issuer.|
|RequesterUpn|string|The User Principal Names of requestor.|
|RequesterUserName|string|The user name of requestor for SMB.|
|AuthorizationDetails|dynamic|Detailed policy information used to authorize the request.|
|SmbPrimarySID|string|Security Identifier of Kerberos Authenticated request|
|UserAgentHeader|string|The User-Agent header value, in quotes.|
|ReferrerHeader|string|The Referer header value.|
|ClientRequestId|string|The x-ms-client-request-id header value of the request.|
|Etag|string|The ETag identifier for the returned object, in quotes.|
|ServiceType|string|The service associated with this request.|
|OperationCount|int|The number of each logged operation that is involved in the request. This count starts with an index of 0. Some requests require more than one operation, such as a request to copy a blob. Most requests perform only one operation.|
|RequestHeaderSize|long|The size of the request header expressed in bytes. If a request is unsuccessful, this value might be empty.|
|RequestBodySize|long|The size of the request packets, expressed in bytes, that are read by the storage service. If a request is unsuccessful, this value might be empty.|
|ResponseHeaderSize|long|The size of the response header expressed in bytes. If a request is unsuccessful, this value might be empty.|
|ResponseBodySize|long|The size of the response packets written by the storage service, in bytes. If a request is unsuccessful, this value may be empty.|
|RequestMd5|string|The value of either the Content-MD5 header or the x-ms-content-md5 header in the request. The MD5 hash value specified in this field represents the content in the request.|
|ResponseMd5|string|The value of the MD5 hash calculated by the storage service.|
|LastModifiedTime|datetime|The Last Modified Time (LMT) for the returned object. This field is empty for operations that can return multiple objects.|
|ConditionsUsed|string|A semicolon-separated list of key-value pairs that represent a condition.|
|ContentLengthHeader|long|The value of the Content-Length header for the request sent to the storage service.|
|Category|string|The category of requested operation.|
|TlsVersion|string|The TLS version used in the connection of request.|
|SmbTreeConnectID|int|The SMB TreeConnectID established at TreeConnect time.|
|SmbPersistentHandleID|long|Persistent HandleID from an SMB2 Create request that survives network reconnects.  Referenced in [MS-SMB2] 2.2.14.1 as SMB2_FILEID.Persistent.|
|SmbVolatileHandleID|long|Volatile HandleID from an SMB2 Create request that is recycled on network reconnects.  Referenced in [MS-SMB2] 2.2.14.1 as SMB2_FILEID.Volatile.|
|SmbMessageID|long|The connection relative MessageId.|
|SmbCreditsConsumed|int|The ingress or egress consumed by the request, in units of 64k.|
|SmbCommandDetail|string|More information about this specific request rather than the general type of request.|
|SmbFileId|long|The FileId associated with file or directory.  Roughly analogous to an NTFS FileId.|
|SmbSessionID|long|The SMB2 SessionId established at SessionSetup time.|
|SmbCommandMajor|int|Value in SMB2_HEADER.Command, and is currently a number between 0 and 18 inclusive.|
|SmbCommandMinor|int|The subclass of  SmbCommandMajor, where appropriate.|
|Type|string||
|_ResourceId|string||
