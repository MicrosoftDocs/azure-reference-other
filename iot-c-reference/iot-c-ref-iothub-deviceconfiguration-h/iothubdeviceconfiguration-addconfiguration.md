# IoTHubDeviceConfiguration_AddConfiguration()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h"](../iot-c-ref-iothub-deviceconfiguration-h.md)  

[`IOTHUB_DEVICE_CONFIGURATION_RESULT`](#iothub__deviceconfiguration_8h_1ac7d4e5e1c224c46fc993541e145b59d6) `[`IoTHubDeviceConfiguration_AddConfiguration`](#iothub__deviceconfiguration_8h_1a89aefeacbcb9da8bdc093a70da75c95c)(`[`IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE`](#iothub__deviceconfiguration_8h_1a6b6d0ee5e70f65ee692e420e50ef805c) serviceClientDeviceConfigurationHandle,const `[`IOTHUB_DEVICE_CONFIGURATION_ADD`](#struct_i_o_t_h_u_b___d_e_v_i_c_e___c_o_n_f_i_g_u_r_a_t_i_o_n___a_d_d) * configurationAdd,`[`IOTHUB_DEVICE_CONFIGURATION`](#struct_i_o_t_h_u_b___d_e_v_i_c_e___c_o_n_f_i_g_u_r_a_t_i_o_n) * configuration)`

Adds the Configuration info to IoT Hub.

#### Parameters
* `serviceClientDeviceConfigurationHandle` The handle created by a call to the create function. 

* `configurationAdd` [IOTHUB_DEVICE_CONFIGURATION_ADD](#struct_i_o_t_h_u_b___d_e_v_i_c_e___c_o_n_f_i_g_u_r_a_t_i_o_n___a_d_d) structure containing the new configuration Id and other optional parameters 

* `configuration` Output parameter, if it is not NULL will contain the created configuration info structure

#### Returns
IOTHUB_DEVICE_CONFIGURATION_RESULT upon success or an error code upon failure.

