# IoTHubRegistryManager_UpdateModule()

Updates a module on IoT Hub.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  
```C
IOTHUB_REGISTRYMANAGER_RESULT IoTHubRegistryManager_UpdateModule(
  IOTHUB_REGISTRYMANAGER_HANDLE  registryManagerHandle,
  IOTHUB_REGISTRY_MODULE_UPDATE  moduleUpdate
);
```

## Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `moduleUpdate` [IOTHUB_REGISTRY_MODULE_UPDATE](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    }) structure containing the new module Id, primaryKey (optional), secondaryKey (optional), authentication method, and status

## Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

