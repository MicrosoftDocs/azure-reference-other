# prov_sc_get_device_registration_state()

Retreives a device registration state from the Provisioning Service.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h](../iot-c-ref-provisioning-service-client-h.md)"  
```C
int prov_sc_get_device_registration_state(
  PROVISIONING_SERVICE_CLIENT_HANDLE  prov_client,
  const char *                        reg_id,
  DEVICE_REGISTRATION_STATE_HANDLE    reg_state_ptr
);
```

## Parameters
* `prov_client` A handle used for connecting to the Provisioning Service. 

* `reg_id` The registration id of the target registration status. 

* `reg_state_ptr` A pointer to a handle for a registration state, to be filled with retreived data.

## Return Value
0 upon success, a non-zero number upon failure.

