# prov_sc_get_individual_enrollment()

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h](../iot-c-ref-provisioning-service-client-h.md)"  

## Syntax

```C
int prov_sc_get_individual_enrollment(
  PROVISIONING_SERVICE_CLIENT_HANDLE  prov_client,
  const char *                        reg_id,
  INDIVIDUAL_ENROLLMENT_HANDLE        enrollment_ptr
);
```

Retreives an individual device enrollment record from the Provisioning Service.

## Parameters
* `prov_client`The handle used for connecting to the Provisioning Service. 

* `reg_id`The registration id of the target individual enrollment. 

* `enrollment`Pointer to a handle for an individual enrollment, to be filled with retreived data.

## Returns
0 upon success, a non-zero number upon failure.

