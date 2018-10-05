# Prov_Device_LL_Register_Device()

\#include "[azure-iot-sdk-c/provisioning_client/inc/azure_prov_client/prov_device_ll_client.h](../iot-c-ref-prov-device-ll-client-h.md)"  

## Syntax

```C
PROV_DEVICE_RESULT Prov_Device_LL_Register_Device(
  PROV_DEVICE_LL_HANDLE                        handle,
  PROV_DEVICE_CLIENT_REGISTER_DEVICE_CALLBACK  register_callback,
  void *                                       user_context,
  PROV_DEVICE_CLIENT_REGISTER_STATUS_CALLBACK  reg_status_cb,
  void *                                       status_user_ctext
);
```

Asynchronous call initiates the registration of a device.

## Parameters
* `handle`The handle created by a call to the create function. 

* `register_callback`The callback that gets called on registration or if an error is encountered 

* `user_context`User specified context that will be provided to the callback 

* `reg_status_cb`An optional registration status callback used to inform the caller of registration status 

* `status_user_ctext`User specified context that will be provided to the registration status callback

## Returns
PROV_DEVICE_RESULT_OK upon success or an error code upon failure

