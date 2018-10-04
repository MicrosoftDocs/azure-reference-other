# IoTHubRegistryManager_UpdateModule()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h"](../iot-c-ref-iothub-registrymanager-h.md)  

**[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_UpdateModule](#iothub__registrymanager_8h_1aa7e34311383a2243e4bc92bb1dd16adc)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,[IOTHUB_REGISTRY_MODULE_UPDATE](#struct_i_o_t_h_u_b___r_e_g_i_s_t_r_y___m_o_d_u_l_e___u_p_d_a_t_e) * moduleUpdate)**

Updates a module on IoT Hub.

#### Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `moduleUpdate` [IOTHUB_REGISTRY_MODULE_UPDATE](#struct_i_o_t_h_u_b___r_e_g_i_s_t_r_y___m_o_d_u_l_e___u_p_d_a_t_e) structure containing the new module Id, primaryKey (optional), secondaryKey (optional), authentication method, and status

#### Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

