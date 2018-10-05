# IoTHubMessage_GetDiagnosticPropertyData()

Gets the DiagnosticData from the IOTHUB_MESSAGE_HANDLE. CAUTION: SDK user should not call it directly, it is for internal use only.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  
```C
const IOTHUB_MESSAGE_DIAGNOSTIC_PROPERTY_DATA* IoTHubMessage_GetDiagnosticPropertyData(
  IOTHUB_MESSAGE_HANDLE  iotHubMessageHandle
);
```

## Parameters
* `iotHubMessageHandle` Handle to the message.

## Returns
A const IOTHUB_MESSAGE_DIAGNOSTIC_PROPERTY_DATA* pointing to the diagnostic property data.

