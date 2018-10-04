# prov_sc_get_device_registration_state()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

## Syntax

```C
int prov_sc_get_device_registration_state(
  PROVISIONING_SERVICE_CLIENT_HANDLE  prov_client,
  const char *                        reg_id,
  DEVICE_REGISTRATION_STATE_HANDLE    reg_state_ptr
);

```

Retreives a device registration state from the Provisioning Service.

#### Parameters
* `prov_client` A handle used for connecting to the Provisioning Service. 

* `reg_id` The registration id of the target registration status. 

* `reg_state_ptr` A pointer to a handle for a registration state, to be filled with retreived data.

#### Returns
0 upon success, a non-zero number upon failure.

