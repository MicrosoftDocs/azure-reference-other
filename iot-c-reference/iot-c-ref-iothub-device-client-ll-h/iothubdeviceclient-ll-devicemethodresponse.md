# IoTHubDeviceClient_LL_DeviceMethodResponse()

This API responds to an asnyc method callback identified the methodId.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h](../iot-c-ref-iothub-device-client-ll-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubDeviceClient_LL_DeviceMethodResponse(
  IOTHUB_DEVICE_CLIENT_LL_HANDLE  iotHubClientHandle,
  METHOD_HANDLE                   methodId,
  const unsigned char *           response,
  size_t                          respSize,
  int                             statusCode
);
```

## Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `methodId` The methodId of the Device Method callback. 

* `response` The response data for the method callback. 

* `response_size` The size of the response data buffer. 

* `status_response` The status response of the method callback.

## Return Value
IOTHUB_CLIENT_OK upon success or an error code upon failure.

