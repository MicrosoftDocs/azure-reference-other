# IoTHubDeviceConfiguration_UpdateConfiguration()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h"](../iot-c-ref-iothub-deviceconfiguration-h.md)  

## Syntax

```C
IOTHUB_DEVICE_CONFIGURATION_RESULT IoTHubDeviceConfiguration_UpdateConfiguration(
  IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE  	serviceClientDeviceConfigurationHandle,
  const                                              	configuration
);

```

Updates the given Configuration in IoT Hub.

#### Parameters
* `serviceClientDeviceConfigurationHandle` The handle created by a call to the create function. 

* `configuration` [IOTHUB_DEVICE_CONFIGURATION](#struct_i_o_t_h_u_b___d_e_v_i_c_e___c_o_n_f_i_g_u_r_a_t_i_o_n) structure containing the new configuration info.

#### Returns
IOTHUB_DEVICE_CONFIGURATION_RESULT upon success or an error code upon failure.

