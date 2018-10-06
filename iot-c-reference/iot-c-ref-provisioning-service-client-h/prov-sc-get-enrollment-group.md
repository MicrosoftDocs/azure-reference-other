# prov_sc_get_enrollment_group()

Retreives a device enrollment group record from the Provisioning Service.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h](../iot-c-ref-provisioning-service-client-h.md)"  
```C
int prov_sc_get_enrollment_group(
  PROVISIONING_SERVICE_CLIENT_HANDLE  prov_client,
  const char *                        group_id,
  ENROLLMENT_GROUP_HANDLE             enrollment_ptr
);
```

## Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `group_id` The enrollment group id of the target enrollment group. 

* `enrollment_ptr` A pointer to a handle for an enrollment group, to be filled with the retreived data.

## Return Value
0 upon success, a non-zero number upon failure.

