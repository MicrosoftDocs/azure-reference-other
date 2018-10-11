# IoTHubMessage_SetContentTypeSystemProperty()

Sets the content-type of the message payload, as per supported values on RFC 2046.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  
```C
IOTHUB_MESSAGE_RESULT IoTHubMessage_SetContentTypeSystemProperty(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle,
  const char *           contentType
);
```

## Parameters
* `iotHubMessageHandle` Handle to the message.

* `contentType` String defining the type of the payload (e.g., text/plain).

## Return Value
An IOTHUB_MESSAGE_RESULT value.

