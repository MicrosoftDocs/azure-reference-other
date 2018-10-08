# IoTHubMessage_GetString()

Returns the null terminated string stored in the message. If the content type of the message is not IOTHUBMESSAGE_STRING then the function returns NULL.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  
```C
const char* IoTHubMessage_GetString(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle
);
```

## Parameters
* `iotHubMessageHandle` Handle to the message.

## Return Value
NULL if an error occurs or a pointer to the stored null terminated string otherwise.

