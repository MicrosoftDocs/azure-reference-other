# IoTHubModuleClient_GetSendStatus()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h"](../iot-c-ref-iothub-module-client-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_GetSendStatus`](#iothub__module__client_8h_1ae000ce091b36687df46e2a2658fa76c6)(`[`IOTHUB_MODULE_CLIENT_HANDLE`](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,`[`IOTHUB_CLIENT_STATUS`](#iothub__client__core__common_8h_1af80b6370369f3c1bb53399deccb4491c) * IoTHubClientStatus)`

This function returns the current sending status for IoTHubClient.

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `IoTHubClientStatus` The sending state is populated at the address pointed at by this parameter. The value will be set to `IoTHubClient_SENDSTATUS_IDLE` if there is currently no item to be sent and `IoTHubClient_SENDSTATUS_BUSY` if there are.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

