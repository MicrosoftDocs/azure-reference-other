# IoTHubRegistryManager_GetDevice_Ex()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h"](../iot-c-ref-iothub-registrymanager-h.md)  

[`IOTHUB_REGISTRYMANAGER_RESULT`](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) `[`IoTHubRegistryManager_GetDevice_Ex`](#iothub__registrymanager_8h_1a3b4ec8fac5715c1d7dcf80d995a4c656)(`[`IOTHUB_REGISTRYMANAGER_HANDLE`](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,const char * deviceId,`[`IOTHUB_DEVICE_EX`](#struct_i_o_t_h_u_b___d_e_v_i_c_e___e_x) * device)`

Gets device info for a given device.

#### Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `deviceId` The Id of the requested device. 

* `device` Input parameter, if it is not NULL will contain the requested device info structure

#### Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

