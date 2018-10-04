# Prov_Device_LL_Register_Device()

\#include ["azure-iot-sdk-c/provisioning_client/inc/azure_prov_client/prov_device_ll_client.h"](../iot-c-ref-prov-device-ll-client-h.md)  

[`PROV_DEVICE_RESULT`](#prov__device__ll__client_8h_1a4e21aaa494a7ff52958e337551fde7eb) `[`Prov_Device_LL_Register_Device`](#prov__device__ll__client_8h_1ad466d9cb0750eefc15bafe006018ae6c)(`[`PROV_DEVICE_LL_HANDLE`](#prov__device__ll__client_8h_1aa6ce77119fc5a0c50d57a97a990cb54f) handle,`[`PROV_DEVICE_CLIENT_REGISTER_DEVICE_CALLBACK`](#prov__device__ll__client_8h_1ac1a30031c36b065d7557ab76e919201f) register_callback,void * user_context,`[`PROV_DEVICE_CLIENT_REGISTER_STATUS_CALLBACK`](#prov__device__ll__client_8h_1a992c5a15ab87f820c87ca2121cb1fd14) reg_status_cb,void * status_user_ctext)`

Asynchronous call initiates the registration of a device.

#### Parameters
* `handle` The handle created by a call to the create function. 

* `register_callback` The callback that gets called on registration or if an error is encountered 

* `user_context` User specified context that will be provided to the callback 

* `reg_status_cb` An optional registration status callback used to inform the caller of registration status 

* `status_user_ctext` User specified context that will be provided to the registration status callback

#### Returns
PROV_DEVICE_RESULT_OK upon success or an error code upon failure

