# IoTHubDeviceClient_CreateWithTransport()

Creates a IoT Hub client for communication with an existing IoT Hub using the specified parameters.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h](../iot-c-ref-iothub-device-client-h.md)"  
```C
IOTHUB_DEVICE_CLIENT_HANDLE IoTHubDeviceClient_CreateWithTransport(
  TRANSPORT_HANDLE  transportHandle,
  const             config
);
```

## Parameters
* `transportHandle` TRANSPORT_HANDLE which represents a connection. 

* `config` Pointer to an `[IOTHUB_CLIENT_CONFIG](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    })` structure

The API allows sharing of a connection across multiple devices. This is a blocking call.

## Returns
A non-NULL `IOTHUB_DEVICE_CLIENT_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

