# prov_sc_create_or_update_individual_enrollment()

Creates or updates an individual device enrollment record on the Provisioning Service, reflecting the changes in the given struct.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h](../iot-c-ref-provisioning-service-client-h.md)"  
```C
int prov_sc_create_or_update_individual_enrollment(
  PROVISIONING_SERVICE_CLIENT_HANDLE  prov_client,
  INDIVIDUAL_ENROLLMENT_HANDLE        enrollment_ptr
);
```

## Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `enrollment_ptr` Pointer to a handle for a new or updated individual enrollment (will be updated with new info from the Provisioning Service).

## Returns
0 upon success, a non-zero number upon failure.

