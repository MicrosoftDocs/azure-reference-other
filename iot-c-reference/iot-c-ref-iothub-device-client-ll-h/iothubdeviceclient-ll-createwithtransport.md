# IoTHubDeviceClient_LL_CreateWithTransport()

Creates a IoT Hub client for communication with an existing IoT Hub using an existing transport.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h](../iot-c-ref-iothub-device-client-ll-h.md)"  
```C
IOTHUB_DEVICE_CLIENT_LL_HANDLE IoTHubDeviceClient_LL_CreateWithTransport(
  const   config
);
```

## Parameters
* `config` Pointer to an `[IOTHUB_CLIENT_DEVICE_CONFIG](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    })` structure

The API *allows* sharing of a connection across multiple devices. This is a blocking call.

## Returns
A non-NULL `IOTHUB_DEVICE_CLIENT_LL_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

