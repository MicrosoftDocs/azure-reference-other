# IoTHubMessage_SetContentTypeSystemProperty()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

## Syntax

```C
IOTHUB_MESSAGE_RESULT IoTHubMessage_SetContentTypeSystemProperty(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle,
  const char *           contentType
);

```

Sets the content-type of the message payload, as per supported values on RFC 2046.

#### Parameters
* `iotHubMessageHandle` Handle to the message.

* `contentType` String defining the type of the payload (e.g., text/plain).

#### Returns
An `IOTHUB_MESSAGE_RESULT` value.

