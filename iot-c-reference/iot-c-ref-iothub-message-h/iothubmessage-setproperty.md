# IoTHubMessage_SetProperty()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  

## Syntax

```C
IOTHUB_MESSAGE_RESULT IoTHubMessage_SetProperty(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle,
  const char *           key,
  const char *           value);
```

Sets a property on a Iothub Message.

## Parameters
* `iotHubMessageHandle`Handle to the message.

* `key`name of the property to set. Note that when sending messages via the HTTP transport, this value must not contain spaces.

* `value`of the property to set.

## Returns
An `IOTHUB_MESSAGE_RESULT` value indicating the result of setting the property.

