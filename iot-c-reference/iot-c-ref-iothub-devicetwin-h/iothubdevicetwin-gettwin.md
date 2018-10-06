# IoTHubDeviceTwin_GetTwin()

Retrieves the given device's twin info.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_devicetwin.h](../iot-c-ref-iothub-devicetwin-h.md)"  
```C
char* IoTHubDeviceTwin_GetTwin(
  IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE  serviceClientDeviceTwinHandle,
  const char *                              deviceId
);
```

## Parameters
* `serviceClientDeviceTwinHandle` The handle created by a call to the create function. 

* `deviceId` The device name (id) to retrieve twin info for.

## Return Value
A non-NULL char* containing device twin info upon success or NULL upon failure.

