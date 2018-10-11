# IoTHubClientCore_SetDeviceMethodCallback()

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_core.h](../iot-c-ref-iothub-client-core-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubClientCore_SetDeviceMethodCallback(
  IOTHUB_CLIENT_CORE_HANDLE                   iotHubClientHandle,
  IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC  deviceMethodCallback,
  void *                                      userContextCallback
);
```

