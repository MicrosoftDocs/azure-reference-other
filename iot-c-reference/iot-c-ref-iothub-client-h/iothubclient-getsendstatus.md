# IoTHubClient_GetSendStatus()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client.h"](../iot-c-ref-iothub-client-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_GetSendStatus](#iothub__client_8h_1a692ed29a02e5842a60db1b3c0ce1b186)([IOTHUB_CLIENT_HANDLE](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,[IOTHUB_CLIENT_STATUS](#iothub__client__core__common_8h_1af80b6370369f3c1bb53399deccb4491c) * iotHubClientStatus)**

This function returns the current sending status for IoTHubClient.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `iotHubClientStatus` The sending state is populated at the address pointed at by this parameter. The value will be set to `IOTHUBCLIENT_SENDSTATUS_IDLE` if there is currently no item to be sent and `IOTHUBCLIENT_SENDSTATUS_BUSY` if there are.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

