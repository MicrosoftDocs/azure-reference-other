# IoTHubMessage_SetDiagnosticPropertyData()

Sets the DiagnosticData for the IOTHUB_MESSAGE_HANDLE. CAUTION: SDK user should not call it directly, it is for internal use only.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  
```C
IOTHUB_MESSAGE_RESULT IoTHubMessage_SetDiagnosticPropertyData(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle,
  const                  diagnosticData
);
```

## Parameters
* `iotHubMessageHandle` Handle to the message. 

* `diagnosticData` Pointer to the memory location of the diagnosticData

## Returns
Returns IOTHUB_MESSAGE_OK if the DiagnosticData was set successfully or an error code otherwise.

