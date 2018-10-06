# IoTHubRegistryManager_FreeDeviceExMembers()

Free members of the [IOTHUB_DEVICE_EX](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    }) structure (NOT the structure itself)

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  
```C
void IoTHubRegistryManager_FreeDeviceExMembers(
  IOTHUB_DEVICE_EX  deviceInfo
);
```

## Parameters
* `deviceInfo` The structure to have its members freed.

