# prov_sc_delete_enrollment_group()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

int `[`prov_sc_delete_enrollment_group`](#provisioning__service__client_8h_1a90e867f213b500a9bb4f7ed460574ea2)(`[`PROVISIONING_SERVICE_CLIENT_HANDLE`](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,`[`ENROLLMENT_GROUP_HANDLE`](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment)`

Deletes a device enrollment group record on the Provisioning Service.

#### Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `enrollment` The handle for the target enrollment group

#### Returns
0 upon success, a non-zero number upon failure.

