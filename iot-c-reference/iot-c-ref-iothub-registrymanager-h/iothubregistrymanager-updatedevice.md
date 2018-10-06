# IoTHubRegistryManager_UpdateDevice()

Updates a device on IoT Hub.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  
```C
IOTHUB_REGISTRYMANAGER_RESULT IoTHubRegistryManager_UpdateDevice(
  IOTHUB_REGISTRYMANAGER_HANDLE  registryManagerHandle,
  IOTHUB_REGISTRY_DEVICE_UPDATE  deviceUpdate
);
```

DEPRECATED:: Use IoTHubRegistryManager_UpdateDevice_Ex instead 
## Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `deviceUpdate` [IOTHUB_REGISTRY_DEVICE_UPDATE](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    }) structure containing the new device Id, primaryKey (optional), secondaryKey (optional), authentication method, and status

## Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

