# IoTHubRegistryManager_FreeModuleMembers()

Free members of the [IOTHUB_MODULE](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    }) structure (NOT the structure itself)

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  
```C
void IoTHubRegistryManager_FreeModuleMembers(
  IOTHUB_MODULE  moduleInfo
);
```

## Parameters
* `moduleInfo` The structure to have its members freed.

