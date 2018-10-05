# IoTHubDeviceTwin_Destroy()

Disposes of resources allocated by the IoT Hub IoTHubDeviceTwin_Create.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_devicetwin.h](../iot-c-ref-iothub-devicetwin-h.md)"  
```C
void IoTHubDeviceTwin_Destroy(
  IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE  serviceClientDeviceTwinHandle
);
```

## Parameters
* `serviceClientDeviceTwinHandle` The handle created by a call to the create function.

