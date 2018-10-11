# IoTHubMessage_CreateFromString()

Creates a new IoT hub message from a null terminated string. The type of the message will be set to IOTHUBMESSAGE_STRING.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  
```C
IOTHUB_MESSAGE_HANDLE IoTHubMessage_CreateFromString(
  const char *  source
);
```

## Parameters
* `source` The null terminated string from which the message is to be created.

## Return Value
A valid IOTHUB_MESSAGE_HANDLE if the message was successfully created or NULL in case an error occurs.

