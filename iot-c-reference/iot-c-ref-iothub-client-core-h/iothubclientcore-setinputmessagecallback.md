# IoTHubClientCore_SetInputMessageCallback()

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_core.h](../iot-c-ref-iothub-client-core-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubClientCore_SetInputMessageCallback(
  IOTHUB_CLIENT_CORE_HANDLE             iotHubClientHandle,
  const char *                          inputName,
  IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC  eventHandlerCallback,
  void *                                userContextCallback
);
```

