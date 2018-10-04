# IoTHubRegistryManager_CreateModule()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h"](../iot-c-ref-iothub-registrymanager-h.md)  

**[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_CreateModule](#iothub__registrymanager_8h_1a16cda510d5746eed5d620cb0682f19de)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,const [IOTHUB_REGISTRY_MODULE_CREATE](#struct_i_o_t_h_u_b___r_e_g_i_s_t_r_y___m_o_d_u_l_e___c_r_e_a_t_e) * moduleCreate,[IOTHUB_MODULE](#struct_i_o_t_h_u_b___m_o_d_u_l_e) * module)**

Creates a module on IoT Hub.

#### Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `moduleCreate` [IOTHUB_REGISTRY_MODULE_CREATE](#struct_i_o_t_h_u_b___r_e_g_i_s_t_r_y___m_o_d_u_l_e___c_r_e_a_t_e) structure containing the existing deviceID, new module Id, primaryKey (optional) and secondaryKey (optional) 

* `module` Input parameter, if it is not NULL will contain the created module info structure

#### Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

