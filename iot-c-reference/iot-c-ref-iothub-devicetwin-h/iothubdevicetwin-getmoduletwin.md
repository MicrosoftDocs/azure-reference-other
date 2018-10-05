# IoTHubDeviceTwin_GetModuleTwin()

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_devicetwin.h](../iot-c-ref-iothub-devicetwin-h.md)"  

## Syntax

```C
char* IoTHubDeviceTwin_GetModuleTwin(
  IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE  serviceClientDeviceTwinHandle,

  const char *                              deviceId,

  const char *                              moduleId
);
```

Retrieves the given module's twin info.

## Parameters
* **:serviceClientDeviceTwinHandle** The handle created by a call to the create function. 

* **:deviceId** The device name (id) containing the module to retrieve the twin info for. 

* **:moduleId** The module name (id) to retrieve twin info for.

## Returns
A non-NULL char* containing module twin info upon success or NULL upon failure.

