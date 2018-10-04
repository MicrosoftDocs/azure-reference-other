# IoTHubRegistryManager_GetModuleList()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h"](../iot-c-ref-iothub-registrymanager-h.md)  

**[IOTHUB_REGISTRYMANAGER_RESULT](#iothub__registrymanager_8h_1a0a3cc25ab12c621a78742593871e18b6) [IoTHubRegistryManager_GetModuleList](#iothub__registrymanager_8h_1aec5598e53961fdfc2580a9a33957b99c)([IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) registryManagerHandle,const char * deviceId,[SINGLYLINKEDLIST_HANDLE](#singlylinkedlist_8h_1a355ba061e4132f7817d6d1963d33382a) moduleList,int module_version)**

Gets a list of modules registered on the specified device.

#### Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `deviceId` The device to get a list of modules from 

* `moduleList` The linked list structure to hold the returned modules 

* `module_version` The version of the module structure to return

#### Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

