# IoTHubMessage_GetInputName()

Gets the input name from the IOTHUB_MESSAGE_HANDLE.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  
```C
const char* IoTHubMessage_GetInputName(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle
);
```

## Parameters
* `iotHubMessageHandle` Handle to the message.

## Return Value
A const char* pointing to the Input Id.

