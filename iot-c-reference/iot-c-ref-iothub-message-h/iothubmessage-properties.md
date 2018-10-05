# IoTHubMessage_Properties()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  

## Syntax

```C
MAP_HANDLE IoTHubMessage_Properties(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle);
```

Gets a handle to the message's properties map. Note that when sending messages via the HTTP transport, the key names in the map must not contain spaces.

DEPRECATED: Use IoTHubMessage_SetProperty and IoTHubMessage_GetProperty instead. ** 
## Parameters
* `iotHubMessageHandle`Handle to the message.

## Returns
A `MAP_HANDLE` pointing to the properties map for this message.

