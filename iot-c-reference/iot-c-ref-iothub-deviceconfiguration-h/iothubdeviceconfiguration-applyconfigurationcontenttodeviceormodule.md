# IoTHubDeviceConfiguration_ApplyConfigurationContentToDeviceOrModule()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h"](../iot-c-ref-iothub-deviceconfiguration-h.md)  

**[IOTHUB_DEVICE_CONFIGURATION_RESULT](#iothub__deviceconfiguration_8h_1ac7d4e5e1c224c46fc993541e145b59d6) [IoTHubDeviceConfiguration_ApplyConfigurationContentToDeviceOrModule](#iothub__deviceconfiguration_8h_1a85f9a43f356ef17d453a644d7927940a)([IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE](#iothub__deviceconfiguration_8h_1a6b6d0ee5e70f65ee692e420e50ef805c) serviceClientDeviceConfigurationHandle,const char * deviceOrModuleId,const [IOTHUB_DEVICE_CONFIGURATION_CONTENT](#struct_i_o_t_h_u_b___d_e_v_i_c_e___c_o_n_f_i_g_u_r_a_t_i_o_n___c_o_n_t_e_n_t) * configurationContent)**

Deletes the given Configuration from IoT Hub.

#### Parameters
* `serviceClientDeviceConfigurationHandle` The handle created by a call to the create function. 

* `deviceOrModuleId` The target device or module id for the Configuration content. 

* `configurationContent` The configuration content to be applied.

#### Returns
IOTHUB_DEVICE_CONFIGURATION_RESULT upon success or an error code upon failure.

