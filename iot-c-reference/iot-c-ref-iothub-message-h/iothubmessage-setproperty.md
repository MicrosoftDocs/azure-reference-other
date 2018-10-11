# IoTHubMessage_SetProperty()

Sets a property on a Iothub Message.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  
```C
IOTHUB_MESSAGE_RESULT IoTHubMessage_SetProperty(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle,
  const char *           key,
  const char *           value
);
```

## Parameters
* `iotHubMessageHandle` Handle to the message.

* `key` name of the property to set. Note that when sending messages via the HTTP transport, this value must not contain spaces.

* `value` of the property to set.

## Return Value
An IOTHUB_MESSAGE_RESULT value indicating the result of setting the property.

