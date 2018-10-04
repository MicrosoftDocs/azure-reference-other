# prov_sc_create_or_update_individual_enrollment()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

int `[`prov_sc_create_or_update_individual_enrollment`](#provisioning__service__client_8h_1a6edae25ef4128a0d11c411e50ac70c69)(`[`PROVISIONING_SERVICE_CLIENT_HANDLE`](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,`[`INDIVIDUAL_ENROLLMENT_HANDLE`](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) * enrollment_ptr)`

Creates or updates an individual device enrollment record on the Provisioning Service, reflecting the changes in the given struct.

#### Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `enrollment_ptr` Pointer to a handle for a new or updated individual enrollment (will be updated with new info from the Provisioning Service).

#### Returns
0 upon success, a non-zero number upon failure.

