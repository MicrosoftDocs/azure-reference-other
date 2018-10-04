# IoTHubDeviceClient_DeviceMethodResponse()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h"](../iot-c-ref-iothub-device-client-h.md)  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubDeviceClient_DeviceMethodResponse(
  IOTHUB_DEVICE_CLIENT_HANDLE  iotHubClientHandle,
  METHOD_HANDLE                methodId,
  const unsigned char *        response,
  size_t                       response_size,
  int                          statusCode
);

```

This API responds to an asnyc method callback identified the methodId.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `methodId` The methodId of the Device Method callback. 

* `response` The response data for the method callback. 

* `response_size` The size of the response data buffer. 

* `status_response` The status response of the method callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

