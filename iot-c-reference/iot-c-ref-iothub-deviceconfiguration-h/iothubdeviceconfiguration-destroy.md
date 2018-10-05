# IoTHubDeviceConfiguration_Destroy()

Disposes of resources allocated by the IoT Hub IoTHubDeviceConfiguration_Create.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h](../iot-c-ref-iothub-deviceconfiguration-h.md)"  
```C
void IoTHubDeviceConfiguration_Destroy(
  IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE  serviceClientDeviceConfigurationHandle
);
```

## Parameters
* `serviceClientDeviceConfigurationHandle` The handle created by a call to the create function.

