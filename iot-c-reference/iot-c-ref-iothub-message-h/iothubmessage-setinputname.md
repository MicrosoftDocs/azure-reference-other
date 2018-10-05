# IoTHubMessage_SetInputName()

Sets input for named queues. CAUTION: SDK user should not call it directly, it is for internal use only.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  
```C
IOTHUB_MESSAGE_RESULT IoTHubMessage_SetInputName(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle,
  const char *           inputName
);
```

## Parameters
* `iotHubMessageHandle` Handle to the message. 

* `inputName` Pointer to the queue to input message to

## Returns
Returns IOTHUB_MESSAGE_OK if the DiagnosticData was set successfully or an error code otherwise.

