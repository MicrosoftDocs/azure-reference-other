# Header file iothub_registrymanager.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include "azure_c_shared_utility/crt_abstractions.h"  
\#include ["azure_c_shared_utility/singlylinkedlist.h"](iot-c-ref-singlylinkedlist-h.md)  
\#include ["azure_c_shared_utility/map.h"](iot-c-ref-map-h.md)  
\#include ["iothub_service_client_auth.h"](iot-c-ref-iothub-service-client-auth-h.md)  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IOTHUB_REGISTRYMANAGER_RESULTStrings](./iot-c-ref-iothub-registrymanager-h/iothub-registrymanager-resultstrings.md)            | 
[IOTHUB_REGISTRYMANAGER_RESULT_FromString](./iot-c-ref-iothub-registrymanager-h/iothub-registrymanager-result-fromstring.md)            | 
[IOTHUB_REGISTRYMANAGER_AUTH_METHODStrings](./iot-c-ref-iothub-registrymanager-h/iothub-registrymanager-auth-methodstrings.md)            | 
[IOTHUB_REGISTRYMANAGER_AUTH_METHOD_FromString](./iot-c-ref-iothub-registrymanager-h/iothub-registrymanager-auth-method-fromstring.md)            | 
[IoTHubRegistryManager_FreeDeviceExMembers](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-freedeviceexmembers.md)            | Free members of the [IOTHUB_DEVICE_EX](#struct_i_o_t_h_u_b___d_e_v_i_c_e___e_x) structure (NOT the structure itself)
[IoTHubRegistryManager_FreeModuleMembers](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-freemodulemembers.md)            | Free members of the [IOTHUB_MODULE](#struct_i_o_t_h_u_b___m_o_d_u_l_e) structure (NOT the structure itself)
[IoTHubRegistryManager_Create](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-create.md)            | Creates a IoT Hub Registry Manager handle for use it in consequent APIs.
[IoTHubRegistryManager_Destroy](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-destroy.md)            | Disposes of resources allocated by the IoT Hub Registry Manager.
[IoTHubRegistryManager_CreateDevice_Ex](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-createdevice-ex.md)            | Creates a device on IoT Hub.
[IoTHubRegistryManager_GetDevice_Ex](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getdevice-ex.md)            | Gets device info for a given device.
[IoTHubRegistryManager_UpdateDevice_Ex](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-updatedevice-ex.md)            | Updates a device on IoT Hub.
[IoTHubRegistryManager_DeleteDevice](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-deletedevice.md)            | Deletes a given device.
[IoTHubRegistryManager_GetStatistics](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getstatistics.md)            | Gets the registry statistic info.
[IoTHubRegistryManager_CreateModule](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-createmodule.md)            | Creates a module on IoT Hub.
[IoTHubRegistryManager_GetModule](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getmodule.md)            | Gets module info for a given module.
[IoTHubRegistryManager_UpdateModule](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-updatemodule.md)            | Updates a module on IoT Hub.
[IoTHubRegistryManager_DeleteModule](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-deletemodule.md)            | Deletes a given module.
[IoTHubRegistryManager_GetModuleList](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getmodulelist.md)            | Gets a list of modules registered on the specified device.
[IoTHubRegistryManager_CreateDevice](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-createdevice.md)            | Creates a device on IoT Hub.
[IoTHubRegistryManager_GetDevice](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getdevice.md)            | Gets device info for a given device.
[IoTHubRegistryManager_UpdateDevice](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-updatedevice.md)            | Updates a device on IoT Hub.
[IoTHubRegistryManager_GetDeviceList](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getdevicelist.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IOTHUB_REGISTRYMANAGER_RESULT_VALUES            | 
IOTHUB_REGISTRYMANAGER_AUTH_METHOD_VALUES            | 
IOTHUB_DEVICE_EX_VERSION_1            | 
IOTHUB_REGISTRY_DEVICE_CREATE_EX_VERSION_1            | 
IOTHUB_REGISTRY_DEVICE_UPDATE_EX_VERSION_1            | 
IOTHUB_MODULE_VERSION_1            | 
IOTHUB_REGISTRY_MODULE_CREATE_VERSION_1            | 
IOTHUB_REGISTRY_MODULE_UPDATE_VERSION_1            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
IOTHUB_REGISTRYMANAGER_HANDLE            | Handle to hide struct and use it in consequent APIs.

## Function documentation

#### IOTHUB_REGISTRYMANAGER_RESULTStrings 
const char * [IOTHUB_REGISTRYMANAGER_RESULTStrings](#iothub__registrymanager_8h_1ae140bb2b4820a1a503ec52d953478b6d)([IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) value)

#### IOTHUB_REGISTRYMANAGER_RESULT_FromString 
int [IOTHUB_REGISTRYMANAGER_RESULT_FromString](#iothub__registrymanager_8h_1acb4bf9a8795d44e8e24d79cdf60f033c)(const char * enumAsString,[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) * destination)

#### IOTHUB_REGISTRYMANAGER_AUTH_METHODStrings 
const char * [IOTHUB_REGISTRYMANAGER_AUTH_METHODStrings](#iothub__registrymanager_8h_1a53110a1d833dd488e295c40fcd343829)([IOTHUB_REGISTRYMANAGER_AUTH_METHOD](#iothub__registrymanager_8h_1a839f42c28ae6cb0043a1c54ff5fa150a) value)

#### IOTHUB_REGISTRYMANAGER_AUTH_METHOD_FromString 
int [IOTHUB_REGISTRYMANAGER_AUTH_METHOD_FromString](#iothub__registrymanager_8h_1a4ec289c38af65dfeba8d00a197401c20)(const char * enumAsString,[IOTHUB_REGISTRYMANAGER_AUTH_METHOD](#iothub__registrymanager_8h_1a839f42c28ae6cb0043a1c54ff5fa150a) * destination)

#### IoTHubRegistryManager_FreeDeviceExMembers 
void [IoTHubRegistryManager_FreeDeviceExMembers](#iothub__registrymanager_8h_1a86b46d3b1b6ab655d3c209a988a3ef98)([IOTHUB_DEVICE_EX](#struct_i_o_t_h_u_b___d_e_v_i_c_e___e_x) * deviceInfo)

#### IoTHubRegistryManager_FreeModuleMembers 
void [IoTHubRegistryManager_FreeModuleMembers](#iothub__registrymanager_8h_1a3b947f1378d5daf1284c87270cd06886)([IOTHUB_MODULE](#struct_i_o_t_h_u_b___m_o_d_u_l_e) * moduleInfo)

#### IoTHubRegistryManager_Create 
[IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) [IoTHubRegistryManager_Create](#iothub__registrymanager_8h_1aefe8d92083c2d44591de4350b5bcb03e)([IOTHUB_SERVICE_CLIENT_AUTH_HANDLE](#iothub__service__client__auth_8h_1a47d2f6357931c33108eb9fba95d8730b) serviceClientHandle)

#### IoTHubRegistryManager_Destroy 
void [IoTHubRegistryManager_Destroy](#iothub__registrymanager_8h_1a439fd053e25fcfe2ab3480dbe09ea6da)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle)

#### IoTHubRegistryManager_CreateDevice_Ex 
[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_CreateDevice_Ex](#iothub__registrymanager_8h_1aeab9fd3fa169b1f0113c0bebf34527de)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,const [IOTHUB_REGISTRY_DEVICE_CREATE_EX](#struct_i_o_t_h_u_b___r_e_g_i_s_t_r_y___d_e_v_i_c_e___c_r_e_a_t_e___e_x) * deviceCreate,[IOTHUB_DEVICE_EX](#struct_i_o_t_h_u_b___d_e_v_i_c_e___e_x) * device)

#### IoTHubRegistryManager_GetDevice_Ex 
[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_GetDevice_Ex](#iothub__registrymanager_8h_1a3b4ec8fac5715c1d7dcf80d995a4c656)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,const char * deviceId,[IOTHUB_DEVICE_EX](#struct_i_o_t_h_u_b___d_e_v_i_c_e___e_x) * device)

#### IoTHubRegistryManager_UpdateDevice_Ex 
[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_UpdateDevice_Ex](#iothub__registrymanager_8h_1afc3d98fcb691e2d6e43474109268a31a)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,[IOTHUB_REGISTRY_DEVICE_UPDATE_EX](#struct_i_o_t_h_u_b___r_e_g_i_s_t_r_y___d_e_v_i_c_e___u_p_d_a_t_e___e_x) * deviceUpdate)

#### IoTHubRegistryManager_DeleteDevice 
[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_DeleteDevice](#iothub__registrymanager_8h_1ae483f02f2b90221bf95f29725e8c622e)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,const char * deviceId)

#### IoTHubRegistryManager_GetStatistics 
[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_GetStatistics](#iothub__registrymanager_8h_1aae28c135f862c1113ccfa2b4a7a7ae50)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,[IOTHUB_REGISTRY_STATISTICS](#struct_i_o_t_h_u_b___r_e_g_i_s_t_r_y___s_t_a_t_i_s_t_i_c_s) * registryStatistics)

#### IoTHubRegistryManager_CreateModule 
[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_CreateModule](#iothub__registrymanager_8h_1a16cda510d5746eed5d620cb0682f19de)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,const [IOTHUB_REGISTRY_MODULE_CREATE](#struct_i_o_t_h_u_b___r_e_g_i_s_t_r_y___m_o_d_u_l_e___c_r_e_a_t_e) * moduleCreate,[IOTHUB_MODULE](#struct_i_o_t_h_u_b___m_o_d_u_l_e) * module)

#### IoTHubRegistryManager_GetModule 
[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_GetModule](#iothub__registrymanager_8h_1ac936b20a8342219f1150d6f661b6bac7)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,const char * deviceId,const char * moduleId,[IOTHUB_MODULE](#struct_i_o_t_h_u_b___m_o_d_u_l_e) * module)

#### IoTHubRegistryManager_UpdateModule 
[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_UpdateModule](#iothub__registrymanager_8h_1aa7e34311383a2243e4bc92bb1dd16adc)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,[IOTHUB_REGISTRY_MODULE_UPDATE](#struct_i_o_t_h_u_b___r_e_g_i_s_t_r_y___m_o_d_u_l_e___u_p_d_a_t_e) * moduleUpdate)

#### IoTHubRegistryManager_DeleteModule 
[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_DeleteModule](#iothub__registrymanager_8h_1a72fd8dfdd409964edd700294ddc768a1)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,const char * deviceId,const char * moduleId)

#### IoTHubRegistryManager_GetModuleList 
[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_GetModuleList](#iothub__registrymanager_8h_1aec5598e53961fdfc2580a9a33957b99c)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,const char * deviceId,[SINGLYLINKEDLIST_HANDLE](#singlylinkedlist_8h_1a355ba061e4132f7817d6d1963d33382a) moduleList,int module_version)

#### IoTHubRegistryManager_CreateDevice 
[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_CreateDevice](#iothub__registrymanager_8h_1a806577f9a82dc2d246b03fa4d9eeabf0)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,const [IOTHUB_REGISTRY_DEVICE_CREATE](#struct_i_o_t_h_u_b___r_e_g_i_s_t_r_y___d_e_v_i_c_e___c_r_e_a_t_e) * deviceCreate,[IOTHUB_DEVICE](#struct_i_o_t_h_u_b___d_e_v_i_c_e) * device)

#### IoTHubRegistryManager_GetDevice 
[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_GetDevice](#iothub__registrymanager_8h_1a9104e678b10a93ed12ae353e2c456eac)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,const char * deviceId,[IOTHUB_DEVICE](#struct_i_o_t_h_u_b___d_e_v_i_c_e) * device)

#### IoTHubRegistryManager_UpdateDevice 
[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_UpdateDevice](#iothub__registrymanager_8h_1a7bf46be7898fa20dd3bebd48d89c67bb)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,[IOTHUB_REGISTRY_DEVICE_UPDATE](#struct_i_o_t_h_u_b___r_e_g_i_s_t_r_y___d_e_v_i_c_e___u_p_d_a_t_e) * deviceUpdate)

#### IoTHubRegistryManager_GetDeviceList 
[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_GetDeviceList](#iothub__registrymanager_8h_1a31336290ea2490f044630919bcdfc4f3)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,size_t numberOfDevices,[SINGLYLINKEDLIST_HANDLE](#singlylinkedlist_8h_1a355ba061e4132f7817d6d1963d33382a) deviceList)

