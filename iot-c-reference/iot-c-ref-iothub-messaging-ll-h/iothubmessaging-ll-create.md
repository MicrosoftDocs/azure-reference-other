# IoTHubMessaging_LL_Create()

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging_ll.h](../iot-c-ref-iothub-messaging-ll-h.md)"  

## Syntax

```C
IOTHUB_MESSAGING_HANDLE IoTHubMessaging_LL_Create(
  IOTHUB_SERVICE_CLIENT_AUTH_HANDLE  iotHubMessagingServiceClientHandle
);
```

Creates a IoT Hub Service Client Messaging handle for use it in consequent APIs.

## Parameters
* **:iotHubMessagingServiceClientHandle** Service client handle.

## Returns
A non-NULL `IOTHUB_MESSAGING_CLIENT_HANDLE` value that is used when invoking other functions for IoT Hub DeviceMethod and `NULL` on failure.

