# IoTHubClientCore_SetMessageCallback()

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_core.h](../iot-c-ref-iothub-client-core-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubClientCore_SetMessageCallback(
  IOTHUB_CLIENT_CORE_HANDLE             iotHubClientHandle,
  IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC  messageCallback,
  void *                                userContextCallback
);
```

