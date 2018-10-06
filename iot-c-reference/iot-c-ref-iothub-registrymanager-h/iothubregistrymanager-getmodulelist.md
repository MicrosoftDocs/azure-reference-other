# IoTHubRegistryManager_GetModuleList()

Gets a list of modules registered on the specified device.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  
```C
IOTHUB_REGISTRYMANAGER_RESULT IoTHubRegistryManager_GetModuleList(
  IOTHUB_REGISTRYMANAGER_HANDLE  registryManagerHandle,
  const char *                   deviceId,
  SINGLYLINKEDLIST_HANDLE        moduleList,
  int                            module_version
);
```

## Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `deviceId` The device to get a list of modules from 

* `moduleList` The linked list structure to hold the returned modules 

* `module_version` The version of the module structure to return

## Return Value
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

