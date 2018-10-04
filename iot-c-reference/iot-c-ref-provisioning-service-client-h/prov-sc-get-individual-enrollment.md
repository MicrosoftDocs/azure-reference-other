# prov_sc_get_individual_enrollment()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

int `[`prov_sc_get_individual_enrollment`](#provisioning__service__client_8h_1a65e0cd1c2f31a73eb4417dd897467750)(`[`PROVISIONING_SERVICE_CLIENT_HANDLE`](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,const char * reg_id,`[`INDIVIDUAL_ENROLLMENT_HANDLE`](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) * enrollment_ptr)`

Retreives an individual device enrollment record from the Provisioning Service.

#### Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `reg_id` The registration id of the target individual enrollment. 

* `enrollment` Pointer to a handle for an individual enrollment, to be filled with retreived data.

#### Returns
0 upon success, a non-zero number upon failure.

