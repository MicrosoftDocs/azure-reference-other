# IoTHubMessage_GetMessageId()

Gets the MessageId from the IOTHUB_MESSAGE_HANDLE.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  
```C
const char* IoTHubMessage_GetMessageId(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle
);
```

## Parameters
* `iotHubMessageHandle` Handle to the message.

## Returns
A const char* pointing to the Message Id.

