# IoTHubRegistryManager_DeleteDevice()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h"](../iot-c-ref-iothub-registrymanager-h.md)  

**[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_DeleteDevice](#iothub__registrymanager_8h_1ae483f02f2b90221bf95f29725e8c622e)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,const char * deviceId)**

Deletes a given device.

#### Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `deviceId` The Id of the device to delete.

#### Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

