# IoTHubClientCore_LL_SetInputMessageCallback()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_core_ll.h](../iot-c-ref-iothub-client-core-ll-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClientCore_LL_SetInputMessageCallback(
  IOTHUB_CLIENT_CORE_LL_HANDLE          iotHubClientHandle,
  const char *                          inputName,
  IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC  eventHandlerCallback,
  void *                                userContextCallback
);
```

