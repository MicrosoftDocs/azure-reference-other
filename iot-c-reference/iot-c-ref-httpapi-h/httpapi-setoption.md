# HTTPAPI_SetOption()

Sets the option named optionName bearing the value value for the HTTP_HANDLE handle.

## Syntax

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/httpapi.h](../iot-c-ref-httpapi-h.md)"  
```C
HTTPAPI_RESULT HTTPAPI_SetOption(
  HTTP_HANDLE   handle,
  const char *  optionName,
  const void *  value
);
```

## Parameters
* `handle` The handle to the HTTP connection created via [HTTPAPI_CreateConnection](#undefined). 

* `optionName` A NULL terminated string representing the name of the option. 

* `value` A pointer to the value for the option.

## Return Value
HTTPAPI_OK if initialization is successful or an error code in case it fails.

