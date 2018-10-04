# HTTPAPI_Init()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/httpapi.h"](../iot-c-ref-httpapi-h.md)  

**[HTTPAPI_RESULT](#httpapi_8h_1ae6d85e45d7bb89c3692f17750762557e) [HTTPAPI_Init](#httpapi_8h_1a0a73dc1b76c522a36b0f201d1a80c3d4)(void)**

Global initialization for the HTTP API component.

Platform specific implementations are expected to initialize the underlying HTTP API stacks.

#### Returns
`HTTPAPI_OK` if initialization is successful or an error code in case it fails.

