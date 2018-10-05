# IoTHubMessage_SetConnectionModuleId()

Sets connection module ID. CAUTION: SDK user should not call it directly, it is for internal use only.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  
```C
IOTHUB_MESSAGE_RESULT IoTHubMessage_SetConnectionModuleId(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle,
  const char *           connectionModuleId
);
```

## Parameters
* `iotHubMessageHandle` Handle to the message. 

* `connectionModuleId` Pointer to the module ID of connector

## Returns
Returns IOTHUB_MESSAGE_OK if the DiagnosticData was set successfully or an error code otherwise.

