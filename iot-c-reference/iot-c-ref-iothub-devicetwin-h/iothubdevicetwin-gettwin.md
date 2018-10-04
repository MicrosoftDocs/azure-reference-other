# IoTHubDeviceTwin_GetTwin()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_devicetwin.h"](../iot-c-ref-iothub-devicetwin-h.md)  

char * `[`IoTHubDeviceTwin_GetTwin`](#iothub__devicetwin_8h_1ad582335584a4ddc69f7dbe881dfe723c)(`[`IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE`](#iothub__devicetwin_8h_1a3394032bf6208c794f399ddfd45471c3) serviceClientDeviceTwinHandle,const char * deviceId)`

Retrieves the given device's twin info.

#### Parameters
* `serviceClientDeviceTwinHandle` The handle created by a call to the create function. 

* `deviceId` The device name (id) to retrieve twin info for.

#### Returns
A non-NULL char* containing device twin info upon success or NULL upon failure.

