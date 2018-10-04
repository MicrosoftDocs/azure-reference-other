# IoTHubRegistryManager_CreateDevice_Ex()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h"](../iot-c-ref-iothub-registrymanager-h.md)  

**[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_CreateDevice_Ex](#iothub__registrymanager_8h_1aeab9fd3fa169b1f0113c0bebf34527de)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,const [IOTHUB_REGISTRY_DEVICE_CREATE_EX](#struct_i_o_t_h_u_b___r_e_g_i_s_t_r_y___d_e_v_i_c_e___c_r_e_a_t_e___e_x) * deviceCreate,[IOTHUB_DEVICE_EX](#struct_i_o_t_h_u_b___d_e_v_i_c_e___e_x) * device)**

Creates a device on IoT Hub.

#### Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `deviceCreate` [IOTHUB_REGISTRY_DEVICE_CREATE_EX](#struct_i_o_t_h_u_b___r_e_g_i_s_t_r_y___d_e_v_i_c_e___c_r_e_a_t_e___e_x) structure containing the new device Id, primaryKey (optional) and secondaryKey (optional) 

* `device` Input parameter, if it is not NULL will contain the created device info structure

#### Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

