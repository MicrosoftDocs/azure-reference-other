# IoTHubDeviceTwin_UpdateTwin()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_devicetwin.h"](../iot-c-ref-iothub-devicetwin-h.md)  

**char * [IoTHubDeviceTwin_UpdateTwin](#iothub__devicetwin_8h_1adabb401facb6b2c95024beb2d351c87d)([IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE](#iothub__devicetwin_8h_1a3394032bf6208c794f399ddfd45471c3) serviceClientDeviceTwinHandle,const char * deviceId,const char * deviceTwinJson)**

Updates (partial update) the given device's twin info.

#### Parameters
* `serviceClientDeviceTwinHandle` The handle created by a call to the create function. 

* `deviceId` The device name (id) to update the twin info for. 

* `deviceTwinJson` DeviceTwin JSon string containing the info (tags, desired properties) to update. All well-known read-only members are ignored. Properties provided with value of null are removed from twin's document.

#### Returns
A non-NULL char* containing updated device twin info upon success or NULL upon failure.

