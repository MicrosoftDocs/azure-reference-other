# IoTHubDeviceConfiguration_GetConfiguration()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h"](../iot-c-ref-iothub-deviceconfiguration-h.md)  

[`IOTHUB_DEVICE_CONFIGURATION_RESULT`](#iothub__deviceconfiguration_8h_1ac7d4e5e1c224c46fc993541e145b59d6) `[`IoTHubDeviceConfiguration_GetConfiguration`](#iothub__deviceconfiguration_8h_1ae51909622d06cab524846b36c2424736)(`[`IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE`](#iothub__deviceconfiguration_8h_1a6b6d0ee5e70f65ee692e420e50ef805c) serviceClientDeviceConfigurationHandle,const char * configurationId,`[`IOTHUB_DEVICE_CONFIGURATION`](#struct_i_o_t_h_u_b___d_e_v_i_c_e___c_o_n_f_i_g_u_r_a_t_i_o_n) * configuration)`

Retrieves the Configuration info for specified configurationId from IoT Hub.

#### Parameters
* `serviceClientDeviceConfigurationHandle` The handle created by a call to the create function. 

* `configurationId` The configuration name (id) to retrieve Configuration info for. 

* `configuration` Output parameter, if it is not NULL will contain the requested configuration info structure

#### Returns
IOTHUB_DEVICE_CONFIGURATION_RESULT upon success or an error code upon failure.

