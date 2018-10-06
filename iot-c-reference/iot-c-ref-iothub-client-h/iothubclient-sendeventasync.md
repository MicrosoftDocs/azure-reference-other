# IoTHubClient_SendEventAsync()

Asynchronous call to send the message specified by `eventMessageHandle`.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client.h](../iot-c-ref-iothub-client-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubClient_SendEventAsync(
  IOTHUB_CLIENT_HANDLE                       iotHubClientHandle,
  IOTHUB_MESSAGE_HANDLE                      eventMessageHandle,
  IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK  eventConfirmationCallback,
  void *                                     userContextCallback
);
```

## Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `eventMessageHandle` The handle to an IoT Hub message. 

* `eventConfirmationCallback` The callback specified by the device for receiving confirmation of the delivery of the IoT Hub message. This callback can be expected to invoke the [IoTHubClient_SendEventAsync](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    }) function for the same message in an attempt to retry sending a failing message. The user can specify a `NULL` value here to indicate that no callback is required. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubClient_Destroy](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    }) function from within any callback.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

