# IoTHubDeviceTwin_Create()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_devicetwin.h"](../iot-c-ref-iothub-devicetwin-h.md)  

[`IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE`](#iothub__devicetwin_8h_1a3394032bf6208c794f399ddfd45471c3) `[`IoTHubDeviceTwin_Create`](#iothub__devicetwin_8h_1acdd0485d9a25bb95fa1d2273e5dbffe9)(`[`IOTHUB_SERVICE_CLIENT_AUTH_HANDLE`](#iothub__service__client__auth_8h_1a47d2f6357931c33108eb9fba95d8730b) serviceClientHandle)`

Creates a IoT Hub Service Client DeviceTwin handle for use it in consequent APIs.

#### Parameters
* `serviceClientHandle` Service client handle.

#### Returns
A non-NULL `IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE` value that is used when invoking other functions for IoT Hub DeviceTwin and `NULL` on failure.

