# IoTHubDeviceConfiguration_AddConfiguration()

Adds the Configuration info to IoT Hub.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h](../iot-c-ref-iothub-deviceconfiguration-h.md)"  
```C
IOTHUB_DEVICE_CONFIGURATION_RESULT IoTHubDeviceConfiguration_AddConfiguration(
  IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE  serviceClientDeviceConfigurationHandle,
  const                                              configurationAdd,
  IOTHUB_DEVICE_CONFIGURATION                        configuration
);
```

## Parameters
* `serviceClientDeviceConfigurationHandle` The handle created by a call to the create function. 

* `configurationAdd` [IOTHUB_DEVICE_CONFIGURATION_ADD](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    }) structure containing the new configuration Id and other optional parameters 

* `configuration` Output parameter, if it is not NULL will contain the created configuration info structure

## Returns
IOTHUB_DEVICE_CONFIGURATION_RESULT upon success or an error code upon failure.

