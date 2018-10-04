# prov_sc_delete_device_registration_state()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

## Syntax

```C
int prov_sc_delete_device_registration_state(
  PROVISIONING_SERVICE_CLIENT_HANDLE  prov_client,
  DEVICE_REGISTRATION_STATE_HANDLE    reg_state
);

```

Deletes a device registration state on the Provisioning Service.

#### Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `reg_state` The handle for the target device registration state.

#### Returns
0 upon success, a non-zero number upon failure.

