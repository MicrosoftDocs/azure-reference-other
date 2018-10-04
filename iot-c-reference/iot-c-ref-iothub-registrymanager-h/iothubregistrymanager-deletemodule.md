# IoTHubRegistryManager_DeleteModule()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h"](../iot-c-ref-iothub-registrymanager-h.md)  

[`IOTHUB_REGISTRYMANAGER_RESULT`](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) `[`IoTHubRegistryManager_DeleteModule`](#iothub__registrymanager_8h_1a72fd8dfdd409964edd700294ddc768a1)(`[`IOTHUB_REGISTRYMANAGER_HANDLE`](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,const char * deviceId,const char * moduleId)`

Deletes a given module.

#### Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `deviceId` The Id of the device containing module to delete. 

* `moduleId` The Id of the module to delete.

#### Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

