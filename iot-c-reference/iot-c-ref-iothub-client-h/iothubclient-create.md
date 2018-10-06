# IoTHubClient_Create()

Creates a IoT Hub client for communication with an existing IoT Hub using the specified parameters.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client.h](../iot-c-ref-iothub-client-h.md)"  
```C
IOTHUB_CLIENT_HANDLE IoTHubClient_Create(
  const   config
);
```

## Parameters
* `config` Pointer to an `[IOTHUB_CLIENT_CONFIG](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    })` structure

The API does not allow sharing of a connection across multiple devices. This is a blocking call.

## Returns
A non-NULL `IOTHUB_CLIENT_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

