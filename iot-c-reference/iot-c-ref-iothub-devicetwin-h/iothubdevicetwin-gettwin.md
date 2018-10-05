# IoTHubDeviceTwin_GetTwin()

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_devicetwin.h](../iot-c-ref-iothub-devicetwin-h.md)"  

## Syntax

```C
char* IoTHubDeviceTwin_GetTwin(
  IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE  serviceClientDeviceTwinHandle,
  const char *                              deviceId
);
```

Retrieves the given device's twin info.

## Parameters
* `serviceClientDeviceTwinHandle`The handle created by a call to the create function. 

* `deviceId`The device name (id) to retrieve twin info for.

## Returns
A non-NULL char* containing device twin info upon success or NULL upon failure.

