# IoTHubMessage_SetContentEncodingSystemProperty()

Sets the content-encoding of the message payload, as per supported values on RFC 2616.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  
```C
IOTHUB_MESSAGE_RESULT IoTHubMessage_SetContentEncodingSystemProperty(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle,
  const char *           contentEncoding
);
```

## Parameters
* `iotHubMessageHandle` Handle to the message.

* `contentEncoding` String defining the encoding of the payload (e.g., utf-8).

## Return Value
An IOTHUB_MESSAGE_RESULT value.

