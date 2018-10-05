# IoTHubClient_LL_GetSendStatus()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h](../iot-c-ref-iothub-client-ll-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClient_LL_GetSendStatus(
  IOTHUB_CLIENT_LL_HANDLE  iotHubClientHandle,

  IOTHUB_CLIENT_STATUS     iotHubClientStatus
);
```

This function returns the current sending status for IoTHubClient.

## Parameters
* **:iotHubClientHandle** The handle created by a call to the create function. 

* **:iotHubClientStatus** The sending state is populated at the address pointed at by this parameter. The value will be set to `IOTHUBCLIENT_SENDSTATUS_IDLE` if there is currently no item to be sent and `IOTHUBCLIENT_SENDSTATUS_BUSY` if there are.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

