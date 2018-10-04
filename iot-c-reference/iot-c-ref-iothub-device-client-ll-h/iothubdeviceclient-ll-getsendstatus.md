# IoTHubDeviceClient_LL_GetSendStatus()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h"](../iot-c-ref-iothub-device-client-ll-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_GetSendStatus`](#iothub__device__client__ll_8h_1a3c4083b15ea124427a2846ba4608ba3e)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,`[`IOTHUB_CLIENT_STATUS`](#iothub__client__core__common_8h_1af80b6370369f3c1bb53399deccb4491c) * iotHubClientStatus)`

This function returns the current sending status for IoTHubClient.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `iotHubClientStatus` The sending state is populated at the address pointed at by this parameter. The value will be set to `IOTHUBCLIENT_SENDSTATUS_IDLE` if there is currently no item to be sent and `IOTHUBCLIENT_SENDSTATUS_BUSY` if there are.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

