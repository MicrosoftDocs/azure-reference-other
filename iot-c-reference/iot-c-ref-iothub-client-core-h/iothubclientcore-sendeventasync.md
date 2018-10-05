# IoTHubClientCore_SendEventAsync()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_core.h](../iot-c-ref-iothub-client-core-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClientCore_SendEventAsync(
  IOTHUB_CLIENT_CORE_HANDLE                  iotHubClientHandle,
  IOTHUB_MESSAGE_HANDLE                      eventMessageHandle,
  IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK  eventConfirmationCallback,
  void *                                     userContextCallback
);
```

