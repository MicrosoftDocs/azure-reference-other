# IoTHubDeviceTwin_Destroy()

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_devicetwin.h](../iot-c-ref-iothub-devicetwin-h.md)"  

## Syntax

```C
void IoTHubDeviceTwin_Destroy(
  IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE  serviceClientDeviceTwinHandle
);
```

Disposes of resources allocated by the IoT Hub IoTHubDeviceTwin_Create.

## Parameters
* `serviceClientDeviceTwinHandle`The handle created by a call to the create function.

