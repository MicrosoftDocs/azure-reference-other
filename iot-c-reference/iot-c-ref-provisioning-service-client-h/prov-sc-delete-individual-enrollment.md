# prov_sc_delete_individual_enrollment()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

**int [prov_sc_delete_individual_enrollment](#provisioning__service__client_8h_1a0400a08cea1573b1d46d27bc326e9726)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,[INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)**

Deletes a individual device enrollment record on the Provisioning Service.

#### Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `enrollment` The handle for the target individual enrollment. Will be matched based on registration id and etag.

#### Returns
0 upon success, a non-zero number upon failure.

