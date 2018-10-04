# prov_sc_delete_device_registration_state()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

int `[`prov_sc_delete_device_registration_state`](#provisioning__service__client_8h_1a5928de9ba394895bf2dbf48d3e85543d)(`[`PROVISIONING_SERVICE_CLIENT_HANDLE`](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,`[`DEVICE_REGISTRATION_STATE_HANDLE`](#provisioning__sc__device__registration__state_8h_1a52841b38d699231f85846525109d2804) reg_state)`

Deletes a device registration state on the Provisioning Service.

#### Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `reg_state` The handle for the target device registration state.

#### Returns
0 upon success, a non-zero number upon failure.

