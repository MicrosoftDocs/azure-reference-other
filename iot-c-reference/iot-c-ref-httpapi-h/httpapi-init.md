# HTTPAPI_Init()

Global initialization for the HTTP API component.

## Syntax

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/httpapi.h](../iot-c-ref-httpapi-h.md)"  
```C
HTTPAPI_RESULT HTTPAPI_Init(void
);
```

Platform specific implementations are expected to initialize the underlying HTTP API stacks.

## Return Value
HTTPAPI_OK if initialization is successful or an error code in case it fails.

