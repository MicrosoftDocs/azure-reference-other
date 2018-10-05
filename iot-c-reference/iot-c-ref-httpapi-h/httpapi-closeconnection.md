# HTTPAPI_CloseConnection()

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/httpapi.h](../iot-c-ref-httpapi-h.md)"  

## Syntax

```C
void HTTPAPI_CloseConnection(
  HTTP_HANDLE  handle
);
```

Closes a connection created with [HTTPAPI_CreateConnection](#httpapi_8h_1a96629fdbe1b52a5357da60bb1248b174).

## Parameters
* `handle`The handle to the HTTP connection created via [HTTPAPI_CreateConnection](#httpapi_8h_1a96629fdbe1b52a5357da60bb1248b174).

All resources allocated by [HTTPAPI_CreateConnection](#httpapi_8h_1a96629fdbe1b52a5357da60bb1248b174) should be freed in [HTTPAPI_CloseConnection](#httpapi_8h_1aed5a7f4253357457399d03dad763d904).

