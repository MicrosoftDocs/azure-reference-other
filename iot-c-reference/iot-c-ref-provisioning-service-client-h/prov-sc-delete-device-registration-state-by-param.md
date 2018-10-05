# prov_sc_delete_device_registration_state_by_param()

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h](../iot-c-ref-provisioning-service-client-h.md)"  

## Syntax

```C
int prov_sc_delete_device_registration_state_by_param(
  PROVISIONING_SERVICE_CLIENT_HANDLE  prov_client,
  const char *                        reg_id,
  const char *                        etag
);
```

Deletes a device registration state on the Provisioning Service.

## Parameters
* `prov_client`The handle used for connecting to the Provisioning Service. 

* `reg_id`The registration id of the target registration state. 

* `etag`The etag of the target registration state

## Returns
0 upon success, a non-zero number upon failure.

