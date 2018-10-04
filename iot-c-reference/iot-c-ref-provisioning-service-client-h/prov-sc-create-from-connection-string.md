# prov_sc_create_from_connection_string()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

[`PROVISIONING_SERVICE_CLIENT_HANDLE`](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) `[`prov_sc_create_from_connection_string`](#provisioning__service__client_8h_1a75fab11e046d9b645a8a094aefffd55c)(const char * conn_string)`

Creates a Provisioning Service Client handle for use in consequent APIs.

#### Parameters
* `conn_string` A connection string used to establish connection with the Provisioning Service.

#### Returns
A non-NULL PROVISIONING_SERVICE_CLIENT_HANDLE value that is used when invoking other functions in the Provisioning Service Client and NULL on failure.

