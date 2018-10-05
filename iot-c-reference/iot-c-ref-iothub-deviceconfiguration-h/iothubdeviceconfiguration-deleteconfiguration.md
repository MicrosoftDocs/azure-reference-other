# IoTHubDeviceConfiguration_DeleteConfiguration()

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h](../iot-c-ref-iothub-deviceconfiguration-h.md)"  

## Syntax

```C
IOTHUB_DEVICE_CONFIGURATION_RESULT IoTHubDeviceConfiguration_DeleteConfiguration(
  IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE  serviceClientDeviceConfigurationHandle,

  const char *                                       configurationId
);
```

Deletes the given Configuration from IoT Hub.

## Parameters
* **:serviceClientDeviceConfigurationHandle** The handle created by a call to the create function. 

* **:configurationId** The configuration name (id) to delete Configuration info for.

## Returns
IOTHUB_DEVICE_CONFIGURATION_RESULT upon success or an error code upon failure.

