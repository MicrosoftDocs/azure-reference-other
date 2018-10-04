# IoTHubMessaging_SendAsync()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging.h"](../iot-c-ref-iothub-messaging-h.md)  

[`IOTHUB_MESSAGING_RESULT`](#iothub__messaging__ll_8h_1ac5ac4fdc87db94cc7ddb7773e79290cd) `[`IoTHubMessaging_SendAsync`](#iothub__messaging_8h_1a4393926997e036da151cc2ec2668f4b1)(`[`IOTHUB_MESSAGING_CLIENT_HANDLE`](#iothub__messaging_8h_1a388e756ded834589f37bbd04bf9cc9c0) messagingClientHandle,const char * deviceId,`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) message,`[`IOTHUB_SEND_COMPLETE_CALLBACK`](#iothub__messaging__ll_8h_1a47509c33cdd854fc209df239dcaef5a9) sendCompleteCallback,void * userContextCallback)`

Asynchronous call to send the message to a specified device.

#### Parameters
* `messagingClientHandle` The handle created by a call to the create function. 

* `deviceId` The name (Id) of the device to send the message to. 

* `message` The message to send. 

* `sendCompleteCallback` The callback specified by the user for receiving confirmation of the delivery of the message. The user can specify a `NULL` value here to indicate that no callback is required. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubMessaging_Destroy](#iothub__messaging_8h_1a5714171907353034b3bc60b7a404fc79) or IoTHubMessaging_Close function from within any callback.

#### Returns
IOTHUB_MESSAGING_OK upon success or an error code upon failure.

