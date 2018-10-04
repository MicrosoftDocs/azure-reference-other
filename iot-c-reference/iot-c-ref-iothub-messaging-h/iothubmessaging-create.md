# IoTHubMessaging_Create()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging.h"](../iot-c-ref-iothub-messaging-h.md)  

**[IOTHUB_MESSAGING_CLIENT_HANDLE](#iothub__messaging_8h_1a388e756ded834589f37bbd04bf9cc9c0) [IoTHubMessaging_Create](#iothub__messaging_8h_1a46b00baeeb17c30bcdce5b3680c1fda3)([IOTHUB_SERVICE_CLIENT_AUTH_HANDLE](#iothub__service__client__auth_8h_1a47d2f6357931c33108eb9fba95d8730b) serviceClientHandle)**

Creates a IoT Hub Service Client Messaging handle for use it in consequent APIs.

#### Parameters
* `serviceClientHandle` Service client handle.

#### Returns
A non-NULL `IOTHUB_MESSAGING_CLIENT_HANDLE` value that is used when invoking other functions for IoT Hub DeviceMethod and `NULL` on failure.

