# IoTHubDeviceConfiguration_UpdateConfiguration()

Updates the given Configuration in IoT Hub.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h](../iot-c-ref-iothub-deviceconfiguration-h.md)"  
```C
IOTHUB_DEVICE_CONFIGURATION_RESULT IoTHubDeviceConfiguration_UpdateConfiguration(
  IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE  serviceClientDeviceConfigurationHandle,
  const                                              configuration
);
```

## Parameters
* `serviceClientDeviceConfigurationHandle` The handle created by a call to the create function. 

* `configuration` [IOTHUB_DEVICE_CONFIGURATION](#undefined) structure containing the new configuration info.

## Returns
IOTHUB_DEVICE_CONFIGURATION_RESULT upon success or an error code upon failure.

