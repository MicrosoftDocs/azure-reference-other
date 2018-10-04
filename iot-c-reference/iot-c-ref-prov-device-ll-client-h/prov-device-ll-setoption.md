# Prov_Device_LL_SetOption()

\#include ["azure-iot-sdk-c/provisioning_client/inc/azure_prov_client/prov_device_ll_client.h"](../iot-c-ref-prov-device-ll-client-h.md)  

[`PROV_DEVICE_RESULT`](#prov__device__ll__client_8h_1a4e21aaa494a7ff52958e337551fde7eb) `[`Prov_Device_LL_SetOption`](#prov__device__ll__client_8h_1ae5035b58c14ec28a988f90eee182f0fd)(`[`PROV_DEVICE_LL_HANDLE`](#prov__device__ll__client_8h_1aa6ce77119fc5a0c50d57a97a990cb54f) handle,const char * optionName,const void * value)`

API sets a runtime option identified by parameter optionName to a value pointed to by value.

#### Parameters
* `handle` The handle created by a call to the create function. 

* `optionName` The name of the option to be set 

* `value` A pointer to the value of the option to be set

#### Returns
PROV_DEVICE_RESULT_OK upon success or an error code upon failure

