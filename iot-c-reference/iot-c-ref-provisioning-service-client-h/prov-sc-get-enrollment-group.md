# prov_sc_get_enrollment_group()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

int `[`prov_sc_get_enrollment_group`](#provisioning__service__client_8h_1ab00d4929b1167f3e43e45f5856a48ee3)(`[`PROVISIONING_SERVICE_CLIENT_HANDLE`](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,const char * group_id,`[`ENROLLMENT_GROUP_HANDLE`](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) * enrollment_ptr)`

Retreives a device enrollment group record from the Provisioning Service.

#### Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `group_id` The enrollment group id of the target enrollment group. 

* `enrollment_ptr` A pointer to a handle for an enrollment group, to be filled with the retreived data.

#### Returns
0 upon success, a non-zero number upon failure.

