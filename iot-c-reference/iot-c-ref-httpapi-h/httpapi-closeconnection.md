# HTTPAPI_CloseConnection()

Closes a connection created with [HTTPAPI_CreateConnection](#undefined).

## Syntax

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/httpapi.h](../iot-c-ref-httpapi-h.md)"  
```C
void HTTPAPI_CloseConnection(
  HTTP_HANDLE  handle
);
```

## Parameters
* `handle` The handle to the HTTP connection created via [HTTPAPI_CreateConnection](#undefined).

All resources allocated by [HTTPAPI_CreateConnection](#undefined) should be freed in [HTTPAPI_CloseConnection](#undefined).

