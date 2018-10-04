# prov_sc_delete_device_registration_state_by_param()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

int `[`prov_sc_delete_device_registration_state_by_param`](#provisioning__service__client_8h_1a0afae62d00a4064cc8c639f4f27e5120)(`[`PROVISIONING_SERVICE_CLIENT_HANDLE`](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,const char * reg_id,const char * etag)`

Deletes a device registration state on the Provisioning Service.

#### Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `reg_id` The registration id of the target registration state. 

* `etag` The etag of the target registration state

#### Returns
0 upon success, a non-zero number upon failure.

