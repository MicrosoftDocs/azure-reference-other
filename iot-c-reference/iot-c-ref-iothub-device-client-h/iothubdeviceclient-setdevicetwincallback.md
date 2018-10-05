# IoTHubDeviceClient_SetDeviceTwinCallback()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h](../iot-c-ref-iothub-device-client-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubDeviceClient_SetDeviceTwinCallback(
  IOTHUB_DEVICE_CLIENT_HANDLE         iotHubClientHandle,

  IOTHUB_CLIENT_DEVICE_TWIN_CALLBACK  deviceTwinCallback,

  void *                              userContextCallback
);
```

This API specifies a callback to be used when the device receives a state update.

## Parameters
* **:iotHubClientHandle** The handle created by a call to the create function. 

* **:deviceTwinCallback** The callback specified by the device client to be used for updating the desired state. The callback will be called in response to a request send by the IoTHub services. The payload will be passed to the callback, along with two version numbers:

* Desired:

* LastSeenReported: 

* **:userContextCallback** User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubDeviceClient_Destroy](#iothub__device__client_8h_1a2991e03140462e9cc1606ccf25e8b412) function from within any callback.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

