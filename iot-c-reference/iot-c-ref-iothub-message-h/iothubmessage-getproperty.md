# IoTHubMessage_GetProperty()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  

## Syntax

```C
const char* IoTHubMessage_GetProperty(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle,
  const char *           key
);
```

Gets a IotHub Message's properties item.

## Parameters
* `iotHubMessageHandle`Handle to the message.

* `key`name of the property to retrieve.

## Returns
A string with the property's value, or NULL if it does not exist in the properties list.

