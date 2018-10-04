# IoTHubMessaging_LL_Create()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging_ll.h"](../iot-c-ref-iothub-messaging-ll-h.md)  

**[IOTHUB_MESSAGING_HANDLE](#iothub__messaging__ll_8h_1ad4dd5cf65fd836ab5b053d59148343ff) [IoTHubMessaging_LL_Create](#iothub__messaging__ll_8h_1a5b087a9084627857a9242ca56afbc056)([IOTHUB_SERVICE_CLIENT_AUTH_HANDLE](#iothub__service__client__auth_8h_1a47d2f6357931c33108eb9fba95d8730b) iotHubMessagingServiceClientHandle)**

Creates a IoT Hub Service Client Messaging handle for use it in consequent APIs.

#### Parameters
* `iotHubMessagingServiceClientHandle` Service client handle.

#### Returns
A non-NULL `IOTHUB_MESSAGING_CLIENT_HANDLE` value that is used when invoking other functions for IoT Hub DeviceMethod and `NULL` on failure.

