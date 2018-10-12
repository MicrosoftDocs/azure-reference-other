# IoTHubModuleClient_GetSendStatus()

This function returns the current sending status for IoTHubClient.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h](../iot-c-ref-iothub-module-client-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_GetSendStatus(
  IOTHUB_MODULE_CLIENT_HANDLE  iotHubModuleClientHandle,
  IOTHUB_CLIENT_STATUS         IoTHubClientStatus
);
```

## Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `IoTHubClientStatus` The sending state is populated at the address pointed at by this parameter. The value will be set to IoTHubClient_SENDSTATUS_IDLE if there is currently no item to be sent and IoTHubClient_SENDSTATUS_BUSY if there are.

## Return Value
IOTHUB_CLIENT_OK upon success or an error code upon failure.

