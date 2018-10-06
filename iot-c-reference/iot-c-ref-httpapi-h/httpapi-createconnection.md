# HTTPAPI_CreateConnection()

Creates an HTTPS connection to the host specified by the `hostName` parameter.

## Syntax

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/httpapi.h](../iot-c-ref-httpapi-h.md)"  
```C
HTTP_HANDLE HTTPAPI_CreateConnection(
  const char *  hostName
);
```

## Parameters
* `hostName` Name of the host.

This function returns a handle to the newly created connection. You can use the handle in subsequent calls to execute specific HTTP calls using [HTTPAPI_ExecuteRequest](#undefined).

## Return Value
A `HTTP_HANDLE` to the newly created connection or `NULL` in case an error occurs.

