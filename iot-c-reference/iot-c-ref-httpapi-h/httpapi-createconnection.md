# HTTPAPI_CreateConnection()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/httpapi.h"](../iot-c-ref-httpapi-h.md)  

[`HTTP_HANDLE`](#httpapi_8h_1a3b2d2d7095a41a942705e437133d35dc) `[`HTTPAPI_CreateConnection`](#httpapi_8h_1a96629fdbe1b52a5357da60bb1248b174)(const char * hostName)`

Creates an HTTPS connection to the host specified by the `hostName` parameter.

#### Parameters
* `hostName` Name of the host.

This function returns a handle to the newly created connection. You can use the handle in subsequent calls to execute specific HTTP calls using [HTTPAPI_ExecuteRequest](#httpapi_8h_1afa60b8d96e73b2fe592b591208ef66b1).

#### Returns
A `HTTP_HANDLE` to the newly created connection or `NULL` in case an error occurs.

