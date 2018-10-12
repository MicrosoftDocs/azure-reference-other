# Prov_Device_LL_SetOption()

API sets a runtime option identified by parameter optionName to a value pointed to by value.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_client/inc/azure_prov_client/prov_device_ll_client.h](../iot-c-ref-prov-device-ll-client-h.md)"  
```C
PROV_DEVICE_RESULT Prov_Device_LL_SetOption(
  PROV_DEVICE_LL_HANDLE  handle,
  const char *           optionName,
  const void *           value
);
```

## Parameters
* `handle` The handle created by a call to the create function. 

* `optionName` The name of the option to be set 

* `value` A pointer to the value of the option to be set

## Return Value
PROV_DEVICE_RESULT_OK upon success or an error code upon failure

