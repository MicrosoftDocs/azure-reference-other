# IoTHubDeviceMethod_InvokeModule()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_devicemethod.h"](../iot-c-ref-iothub-devicemethod-h.md)  

## Syntax

```C
IOTHUB_DEVICE_METHOD_RESULT IoTHubDeviceMethod_InvokeModule(
  IOTHUB_SERVICE_CLIENT_DEVICE_METHOD_HANDLE	serviceClientDeviceMethodHandle,
  const char *	deviceId,
  const char *	moduleId,
  const char *	methodName,
  const char *	methodPayload,
  unsigned int	timeout,
  int *	responseStatus,
  unsigned char **	responsePayload,
  size_t *	responsePayloadSize
);

```

Call a method on device and a module with a given payload.

#### Parameters
* `serviceClientDeviceMethodHandle` The handle created by a call to the create function. 

* `deviceId` The device name (id) to call a method on. 

* `moduleId` The module name (id) to call a method on. 

* `methodName` The method name to call. 

* `methodPayload` The message payload to send. 

* `timeout` Time before IoTHubDeviceMethod_InvokeModule times out. 

* `responseStatus` Response status code from invocation. 

* `responsePayload` Output buffer for response payload. 

* `responsePayloadSize` String length of responsePayload.

#### Returns
An IOTHUB_DEVICE_METHOD_RESULT containing the return status.

