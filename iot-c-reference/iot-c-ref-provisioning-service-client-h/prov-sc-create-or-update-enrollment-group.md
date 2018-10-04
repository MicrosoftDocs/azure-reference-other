# prov_sc_create_or_update_enrollment_group()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

**int [prov_sc_create_or_update_enrollment_group](#provisioning__service__client_8h_1a1b63f862fdde65f6f82e3b2cfc0cf9d0)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,[ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) * enrollment_ptr)**

Creates or updates a device enrollment group record on the Provisioning Service.

#### Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `enrollment_ptr` Pointer to a handle for a new or updated enrollment group.

#### Returns
0 upon success, a non-zero number upon failure.

