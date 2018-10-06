# IoTHubDeviceConfiguration_FreeConfigurationMembers()

Free members of the [IOTHUB_DEVICE_CONFIGURATION](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    }) structure (NOT the structure itself)

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h](../iot-c-ref-iothub-deviceconfiguration-h.md)"  
```C
void IoTHubDeviceConfiguration_FreeConfigurationMembers(
  IOTHUB_DEVICE_CONFIGURATION  configuration
);
```

## Parameters
* `configuration` The structure to have its members freed.

