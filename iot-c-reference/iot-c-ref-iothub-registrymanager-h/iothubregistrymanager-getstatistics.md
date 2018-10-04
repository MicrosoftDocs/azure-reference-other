# IoTHubRegistryManager_GetStatistics()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h"](../iot-c-ref-iothub-registrymanager-h.md)  

**[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_GetStatistics](#iothub__registrymanager_8h_1aae28c135f862c1113ccfa2b4a7a7ae50)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,[IOTHUB_REGISTRY_STATISTICS](#struct_i_o_t_h_u_b___r_e_g_i_s_t_r_y___s_t_a_t_i_s_t_i_c_s) * registryStatistics)**

Gets the registry statistic info.

#### Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `registryStatistics` Input parameter, if it is not NULL will contain the requested registry info.

#### Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

