# IoTHubRegistryManager_CreateDevice()

Creates a device on IoT Hub.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  
```C
IOTHUB_REGISTRYMANAGER_RESULT IoTHubRegistryManager_CreateDevice(
  IOTHUB_REGISTRYMANAGER_HANDLE  registryManagerHandle,
  const                          deviceCreate,
  IOTHUB_DEVICE                  device
);
```

DEPRECATED:: Use IoTHubRegistryManager_CreateDevice_Ex instead 
## Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `deviceCreate` [IOTHUB_REGISTRY_DEVICE_CREATE](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    }) structure containing the new device Id, primaryKey (optional) and secondaryKey (optional) 

* `device` Input parameter, if it is not NULL will contain the created device info structure

## Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

