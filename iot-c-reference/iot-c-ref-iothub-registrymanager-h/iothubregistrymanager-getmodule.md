# IoTHubRegistryManager_GetModule()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h"](../iot-c-ref-iothub-registrymanager-h.md)  

[`IOTHUB_REGISTRYMANAGER_RESULT`](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) `[`IoTHubRegistryManager_GetModule`](#iothub__registrymanager_8h_1ac936b20a8342219f1150d6f661b6bac7)(`[`IOTHUB_REGISTRYMANAGER_HANDLE`](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,const char * deviceId,const char * moduleId,`[`IOTHUB_MODULE`](#struct_i_o_t_h_u_b___m_o_d_u_l_e) * module)`

Gets module info for a given module.

#### Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `deviceId` The Id of the requested device. 

* `moduleId` The Id of the requested module. 

* `module` Input parameter, if it is not NULL will contain the requested module info structure

#### Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

