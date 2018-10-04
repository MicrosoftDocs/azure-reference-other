# IoTHubDeviceClient_GetSendStatus()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h"](../iot-c-ref-iothub-device-client-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_GetSendStatus](#iothub__device__client_8h_1a1b0ed9ddf82f4a32afc7df469452e0cc)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,[IOTHUB_CLIENT_STATUS](#iothub__client__core__common_8h_1af80b6370369f3c1bb53399deccb4491c) * iotHubClientStatus)**

This function returns the current sending status for IoTHubClient.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `iotHubClientStatus` The sending state is populated at the address pointed at by this parameter. The value will be set to `IOTHUBCLIENT_SENDSTATUS_IDLE` if there is currently no item to be sent and `IOTHUBCLIENT_SENDSTATUS_BUSY` if there are.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

