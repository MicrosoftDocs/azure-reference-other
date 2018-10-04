# IoTHubDeviceMethod_Create()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_devicemethod.h"](../iot-c-ref-iothub-devicemethod-h.md)  

[`IOTHUB_SERVICE_CLIENT_DEVICE_METHOD_HANDLE`](#iothub__devicemethod_8h_1a06b6ee10c1627d4f7463c4204490051a) `[`IoTHubDeviceMethod_Create`](#iothub__devicemethod_8h_1a30d7823cef3cfd35ff3e2da3db9c71bf)(`[`IOTHUB_SERVICE_CLIENT_AUTH_HANDLE`](#iothub__service__client__auth_8h_1a47d2f6357931c33108eb9fba95d8730b) serviceClientHandle)`

Creates a IoT Hub Service Client DeviceMethod handle for use it in consequent APIs.

#### Parameters
* `serviceClientHandle` Service client handle.

#### Returns
A non-NULL `IOTHUB_SERVICE_CLIENT_DEVICE_METHOD_HANDLE` value that is used when invoking other functions for IoT Hub DeviceMethod and `NULL` on failure.

