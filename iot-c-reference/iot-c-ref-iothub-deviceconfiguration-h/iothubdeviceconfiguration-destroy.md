# IoTHubDeviceConfiguration_Destroy()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h"](../iot-c-ref-iothub-deviceconfiguration-h.md)  

## Syntax

```C
void IoTHubDeviceConfiguration_Destroy(
  IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE  	serviceClientDeviceConfigurationHandle
);

```

Disposes of resources allocated by the IoT Hub IoTHubDeviceConfiguration_Create.

#### Parameters
* `serviceClientDeviceConfigurationHandle` The handle created by a call to the create function.

