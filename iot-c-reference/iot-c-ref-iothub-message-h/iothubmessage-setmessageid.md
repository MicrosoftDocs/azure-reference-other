# IoTHubMessage_SetMessageId()

Sets the MessageId for the IOTHUB_MESSAGE_HANDLE.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  
```C
IOTHUB_MESSAGE_RESULT IoTHubMessage_SetMessageId(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle,
  const char *           messageId
);
```

## Parameters
* `iotHubMessageHandle` Handle to the message. 

* `messageId` Pointer to the memory location of the messageId

## Returns
Returns IOTHUB_MESSAGE_OK if the messageId was set successfully or an error code otherwise.

