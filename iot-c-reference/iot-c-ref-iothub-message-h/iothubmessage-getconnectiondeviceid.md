# IoTHubMessage_GetConnectionDeviceId()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  

## Syntax

```C
const char* IoTHubMessage_GetConnectionDeviceId(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle);
```

Gets the connection device ID from the IOTHUB_MESSAGE_HANDLE.

## Parameters
* `iotHubMessageHandle`Handle to the message.

## Returns
A const char* pointing to the connection device Id.

