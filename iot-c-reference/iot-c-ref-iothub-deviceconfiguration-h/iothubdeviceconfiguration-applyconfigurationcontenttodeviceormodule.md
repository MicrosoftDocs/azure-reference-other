# IoTHubDeviceConfiguration_ApplyConfigurationContentToDeviceOrModule()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h"](../iot-c-ref-iothub-deviceconfiguration-h.md)  

## Syntax

```C
IOTHUB_DEVICE_CONFIGURATION_RESULT IoTHubDeviceConfiguration_ApplyConfigurationContentToDeviceOrModule(
  IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE  serviceClientDeviceConfigurationHandle,
  const char *                                       deviceOrModuleId,
  const                                              configurationContent
);

```

Deletes the given Configuration from IoT Hub.

#### Parameters
* `serviceClientDeviceConfigurationHandle` The handle created by a call to the create function. 

* `deviceOrModuleId` The target device or module id for the Configuration content. 

* `configurationContent` The configuration content to be applied.

#### Returns
IOTHUB_DEVICE_CONFIGURATION_RESULT upon success or an error code upon failure.

