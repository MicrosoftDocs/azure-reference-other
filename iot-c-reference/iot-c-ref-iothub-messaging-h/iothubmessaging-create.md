# IoTHubMessaging_Create()

Creates a IoT Hub Service Client Messaging handle for use it in consequent APIs.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging.h](../iot-c-ref-iothub-messaging-h.md)"  
```C
IOTHUB_MESSAGING_CLIENT_HANDLE IoTHubMessaging_Create(
  IOTHUB_SERVICE_CLIENT_AUTH_HANDLE  serviceClientHandle
);
```

## Parameters
* `serviceClientHandle` Service client handle.

## Returns
A non-NULL `IOTHUB_MESSAGING_CLIENT_HANDLE` value that is used when invoking other functions for IoT Hub DeviceMethod and `NULL` on failure.

