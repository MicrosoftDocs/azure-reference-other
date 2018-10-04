# prov_sc_get_device_registration_state()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

**int [prov_sc_get_device_registration_state](#provisioning__service__client_8h_1a7b9036be3cfe96fb3aec21801f9e5e8a)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,const char * reg_id,[DEVICE_REGISTRATION_STATE_HANDLE](#provisioning__sc__device__registration__state_8h_1a52841b38d699231f85846525109d2804) * reg_state_ptr)**

Retreives a device registration state from the Provisioning Service.

#### Parameters
* `prov_client` A handle used for connecting to the Provisioning Service. 

* `reg_id` The registration id of the target registration status. 

* `reg_state_ptr` A pointer to a handle for a registration state, to be filled with retreived data.

#### Returns
0 upon success, a non-zero number upon failure.

