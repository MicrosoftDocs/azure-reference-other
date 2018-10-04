# IoTHubDeviceMethod_Invoke()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_devicemethod.h"](../iot-c-ref-iothub-devicemethod-h.md)  

**[IOTHUB_DEVICE_METHOD_RESULT](#iothub__devicemethod_8h_1a8adffbffc2f6e136f8406c5ef396602d) [IoTHubDeviceMethod_Invoke](#iothub__devicemethod_8h_1abdfab207152397a0c843d12a0db4bbf8)([IOTHUB_SERVICE_CLIENT_DEVICE_METHOD_HANDLE](#iothub__devicemethod_8h_1a06b6ee10c1627d4f7463c4204490051a) serviceClientDeviceMethodHandle,const char * deviceId,const char * methodName,const char * methodPayload,unsigned int timeout,int * responseStatus,unsigned char ** responsePayload,size_t * responsePayloadSize)**

Call a method on device with a given payload.

#### Parameters
* `serviceClientDeviceMethodHandle` The handle created by a call to the create function. 

* `deviceId` The device name (id) to call a method on. 

* `methodName` The method name to call. 

* `methodPayload` The message payload to send. 

* `response` Output buffer for response payload. 

* `timeout` Time before IoTHubDeviceMethod_InvokeModule times out. 

* `responseStatus` Response status code from invocation 

* `responsePayload` Output buffer for response payload. 

* `responsePayloadSize` String length of responsePayload.

#### Returns
An IOTHUB_DEVICE_METHOD_RESULT containing the return status.

