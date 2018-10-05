# prov_sc_delete_enrollment_group_by_param()

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h](../iot-c-ref-provisioning-service-client-h.md)"  

## Syntax

```C
int prov_sc_delete_enrollment_group_by_param(
  PROVISIONING_SERVICE_CLIENT_HANDLE  prov_client,
  const char *                        group_id,
  const char *                        etag
);
```

Deletes a device enrollment group record on the Provisioning Service.

## Parameters
* `prov_client`The handle used for connecting to the Provisioning Service. 

* `group_id`The enrollment group id of the target enrollment group. 

* `etag`The etag of the target enrollment group. If given as "*", will match any etag.

## Returns
0 upon success, a non-zero number upon failure.

