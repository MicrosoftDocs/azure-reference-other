# IoTHubMessage_CreateFromString()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

## Syntax

```C
IOTHUB_MESSAGE_HANDLE IoTHubMessage_CreateFromString(
  const char *	source
);

```

Creates a new IoT hub message from a null terminated string. The type of the message will be set to `IOTHUBMESSAGE_STRING`.

#### Parameters
* `source` The null terminated string from which the message is to be created.

#### Returns
A valid `IOTHUB_MESSAGE_HANDLE` if the message was successfully created or `NULL` in case an error occurs.

