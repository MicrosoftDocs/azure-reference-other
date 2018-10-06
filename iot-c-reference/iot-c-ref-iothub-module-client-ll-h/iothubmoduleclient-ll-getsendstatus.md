# IoTHubModuleClient_LL_GetSendStatus()

This function returns the current sending status for IoTHubClient.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h](../iot-c-ref-iothub-module-client-ll-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_LL_GetSendStatus(
  IOTHUB_MODULE_CLIENT_LL_HANDLE  iotHubModuleClientHandle,
  IOTHUB_CLIENT_STATUS            iotHubClientStatus
);
```

## Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `iotHubClientStatus` The sending state is populated at the address pointed at by this parameter. The value will be set to `IOTHUBCLIENT_SENDSTATUS_IDLE` if there is currently no item to be sent and `IOTHUBCLIENT_SENDSTATUS_BUSY` if there are.

## Return Value
IOTHUB_CLIENT_OK upon success or an error code upon failure.

