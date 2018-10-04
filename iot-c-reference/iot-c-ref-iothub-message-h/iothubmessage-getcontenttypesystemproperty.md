# IoTHubMessage_GetContentTypeSystemProperty()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

## Syntax

```C
const char* IoTHubMessage_GetContentTypeSystemProperty(
  IOTHUB_MESSAGE_HANDLE  	iotHubMessageHandle
);

```

Returns the content-type of the message payload, if defined.

#### Parameters
* `iotHubMessageHandle` Handle to the message.

#### Returns
A string with the content-type value if defined (or NULL otherwise).

