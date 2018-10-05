# IoTHubMessage_GetString()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  

## Syntax

```C
const char* IoTHubMessage_GetString(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle);
```

Returns the null terminated string stored in the message. If the content type of the message is not `IOTHUBMESSAGE_STRING` then the function returns `NULL`.

## Parameters
* `iotHubMessageHandle`Handle to the message.

## Returns
`NULL` if an error occurs or a pointer to the stored null terminated string otherwise.

