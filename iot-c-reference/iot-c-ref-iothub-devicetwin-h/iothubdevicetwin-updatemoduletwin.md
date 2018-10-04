# IoTHubDeviceTwin_UpdateModuleTwin()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_devicetwin.h"](../iot-c-ref-iothub-devicetwin-h.md)  

## Syntax

```C
char* IoTHubDeviceTwin_UpdateModuleTwin(
  IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE  serviceClientDeviceTwinHandle,
  const char *                              deviceId,
  const char *                              moduleId,
  const char *                              moduleTwinJson
);

```

Updates (partial update) the given module's twin info.

#### Parameters
* `serviceClientDeviceTwinHandle` The handle created by a call to the create function. 

* `deviceId` The device name (id) containing the module to update. 

* `moduleId` The module name (id) to update the twin info for. 

* `moduleTwinJson` ModuleTwin JSon string containing the info (tags, desired properties) to update. All well-known read-only members are ignored. Properties provided with value of null are removed from twin's document.

#### Returns
A non-NULL char* containing updated module twin info upon success or NULL upon failure.

