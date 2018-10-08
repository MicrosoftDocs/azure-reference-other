# IoTHubMessage_GetContentType()

Returns the content type of the message given by parameter iotHubMessageHandle.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  
```C
IOTHUBMESSAGE_CONTENT_TYPE IoTHubMessage_GetContentType(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle
);
```

## Parameters
* `iotHubMessageHandle` Handle to the message.

## Remarks
This function retrieves the standardized type of the payload, which indicates if iotHubMessageHandle was created using a String or a Byte Array.

## Return Value
An IOTHUBMESSAGE_CONTENT_TYPE value.

