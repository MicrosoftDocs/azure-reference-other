# IoTHubClientCore_LL_SendEventToOutputAsync()

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_core_ll.h](../iot-c-ref-iothub-client-core-ll-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubClientCore_LL_SendEventToOutputAsync(
  IOTHUB_CLIENT_CORE_LL_HANDLE               iotHubClientHandle,
  IOTHUB_MESSAGE_HANDLE                      eventMessageHandle,
  const char *                               outputName,
  IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK  eventConfirmationCallback,
  void *                                     userContextCallback
);
```

