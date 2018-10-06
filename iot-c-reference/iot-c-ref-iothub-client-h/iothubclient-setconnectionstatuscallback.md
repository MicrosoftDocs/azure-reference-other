# IoTHubClient_SetConnectionStatusCallback()

Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client.h](../iot-c-ref-iothub-client-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubClient_SetConnectionStatusCallback(
  IOTHUB_CLIENT_HANDLE                      iotHubClientHandle,
  IOTHUB_CLIENT_CONNECTION_STATUS_CALLBACK  connectionStatusCallback,
  void *                                    userContextCallback
);
```

## Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `connectionStatusCallback` The callback specified by the device for receiving updates about the status of the connection to IoT Hub. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubClient_LL_Destroy](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    }) function from within any callback.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

