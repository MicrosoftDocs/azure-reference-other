# IoTHubDeviceClient_LL_SendEventAsync()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h"](../iot-c-ref-iothub-device-client-ll-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_LL_SendEventAsync](#iothub__device__client__ll_8h_1a56cfcb637e1f46cf0f5e6e2bb81457ad)([IOTHUB_DEVICE_CLIENT_LL_HANDLE](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,[IOTHUB_MESSAGE_HANDLE](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) eventMessageHandle,[IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK](#iothub__client__core__common_8h_1a41b17fcb2cb70587e3576226561648a0) eventConfirmationCallback,void * userContextCallback)**

Asynchronous call to send the message specified by `eventMessageHandle`.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `eventMessageHandle` The handle to an IoT Hub message. 

* `eventConfirmationCallback` The callback specified by the device for receiving confirmation of the delivery of the IoT Hub message. This callback can be expected to invoke the [IoTHubDeviceClient_LL_SendEventAsync](#iothub__device__client__ll_8h_1a56cfcb637e1f46cf0f5e6e2bb81457ad) function for the same message in an attempt to retry sending a failing message. The user can specify a `NULL` value here to indicate that no callback is required. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubDeviceClient_LL_Destroy](#iothub__device__client__ll_8h_1ad2ac0d9176060dfeee0664668ce87e6f) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

