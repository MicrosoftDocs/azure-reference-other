# HTTPAPI_SetOption()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/httpapi.h"](../iot-c-ref-httpapi-h.md)  

## Syntax

```C
HTTPAPI_RESULT HTTPAPI_SetOption(
  HTTP_HANDLE	handle,
  const char *	optionName,
  const void *	value
);

```

Sets the option named `optionName` bearing the value `value` for the HTTP_HANDLE `handle`.

#### Parameters
* `handle` The handle to the HTTP connection created via [HTTPAPI_CreateConnection](#httpapi_8h_1a96629fdbe1b52a5357da60bb1248b174). 

* `optionName` A `NULL` terminated string representing the name of the option. 

* `value` A pointer to the value for the option.

#### Returns
`HTTPAPI_OK` if initialization is successful or an error code in case it fails.

