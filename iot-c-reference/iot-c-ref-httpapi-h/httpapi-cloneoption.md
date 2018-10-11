# HTTPAPI_CloneOption()

Clones the option named optionName bearing the value value into the pointer savedValue.

## Syntax

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/httpapi.h](../iot-c-ref-httpapi-h.md)"  
```C
HTTPAPI_RESULT HTTPAPI_CloneOption(
  const char *   optionName,
  const void *   value,
  const void **  savedValue
);
```

## Parameters
* `optionName` A NULL terminated string representing the name of the option 

* `value` A pointer to the value of the option. 

* `savedValue` This pointer receives the copy of the value of the option. The copy needs to be free-able.

## Return Value
HTTPAPI_OK if initialization is successful or an error code in case it fails.

