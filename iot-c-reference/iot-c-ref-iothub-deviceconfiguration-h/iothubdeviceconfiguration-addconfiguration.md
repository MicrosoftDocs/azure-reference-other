# IoTHubDeviceConfiguration_AddConfiguration()

Adds the Configuration info to IoT Hub.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h](../iot-c-ref-iothub-deviceconfiguration-h.md)"  
```C
IOTHUB_DEVICE_CONFIGURATION_RESULT IoTHubDeviceConfiguration_AddConfiguration(
  IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE  serviceClientDeviceConfigurationHandle,
  const                                              configurationAdd,
  IOTHUB_DEVICE_CONFIGURATION                        configuration
);
```

## Parameters
* `serviceClientDeviceConfigurationHandle` The handle created by a call to the create function. 

* `configurationAdd` [IOTHUB_DEVICE_CONFIGURATION_ADD](#struct_i_o_t_h_u_b___d_e_v_i_c_e___c_o_n_f_i_g_u_r_a_t_i_o_n___a_d_d) structure containing the new configuration Id and other optional parameters 

* `configuration` Output parameter, if it is not NULL will contain the created configuration info structure

## Returns
IOTHUB_DEVICE_CONFIGURATION_RESULT upon success or an error code upon failure.

