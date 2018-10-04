# prov_sc_delete_individual_enrollment_by_param()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

**int [prov_sc_delete_individual_enrollment_by_param](#provisioning__service__client_8h_1adf594d7256c4917e0aa39e38731b58c2)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,const char * reg_id,const char * etag)**

Deletes an individual device enrollment record on the Provisioning Service.

#### Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `reg_id` The registration id of the target individual enrollment. 

* `etag` The etag of the target individual enrollment. If given as "*", will match any etag. If given as NULL, will be ignored.

#### Returns
0 upon success, a non-zero number upon failure.

