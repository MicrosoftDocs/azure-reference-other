# IoTHubDeviceConfiguration_Create()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h"](../iot-c-ref-iothub-deviceconfiguration-h.md)  

[`IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE`](#iothub__deviceconfiguration_8h_1a6b6d0ee5e70f65ee692e420e50ef805c) `[`IoTHubDeviceConfiguration_Create`](#iothub__deviceconfiguration_8h_1a8dd0eaaa96d7d9c87ab68bb5f78adff9)(`[`IOTHUB_SERVICE_CLIENT_AUTH_HANDLE`](#iothub__service__client__auth_8h_1a47d2f6357931c33108eb9fba95d8730b) serviceClientHandle)`

Creates a IoT Hub Service Client DeviceConfiguration handle for use it in consequent APIs.

#### Parameters
* `serviceClientHandle` Service client handle.

#### Returns
A non-NULL `IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE` value that is used when invoking other functions for IoT Hub DeviceConfiguration and `NULL` on failure.

