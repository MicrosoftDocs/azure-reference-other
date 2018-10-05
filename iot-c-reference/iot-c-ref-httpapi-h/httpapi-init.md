# HTTPAPI_Init()

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/httpapi.h](../iot-c-ref-httpapi-h.md)"  

## Syntax

```C
HTTPAPI_RESULT HTTPAPI_Init(  void);
```

Global initialization for the HTTP API component.

Platform specific implementations are expected to initialize the underlying HTTP API stacks.

## Returns
`HTTPAPI_OK` if initialization is successful or an error code in case it fails.

