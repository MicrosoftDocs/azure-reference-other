# IoTHubMessage_SetOutputName()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  

## Syntax

```C
IOTHUB_MESSAGE_RESULT IoTHubMessage_SetOutputName(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle,
  const char *           outputName);
```

Sets output for named queues. CAUTION: SDK user should not call it directly, it is for internal use only.

## Parameters
* `iotHubMessageHandle`Handle to the message. 

* `outputName`Pointer to the queue to output message to

## Returns
Returns IOTHUB_MESSAGE_OK if the DiagnosticData was set successfully or an error code otherwise.

