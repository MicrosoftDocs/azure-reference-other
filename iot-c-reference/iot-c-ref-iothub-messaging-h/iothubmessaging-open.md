# IoTHubMessaging_Open()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging.h"](../iot-c-ref-iothub-messaging-h.md)  

**[IOTHUB_MESSAGING_RESULT](#iothub__messaging__ll_8h_1ac5ac4fdc87db94cc7ddb7773e79290cd) [IoTHubMessaging_Open](#iothub__messaging_8h_1a8844eceec74a77fc647c83d134e873ef)([IOTHUB_MESSAGING_CLIENT_HANDLE](#iothub__messaging_8h_1a388e756ded834589f37bbd04bf9cc9c0) messagingClientHandle,[IOTHUB_OPEN_COMPLETE_CALLBACK](#iothub__messaging__ll_8h_1a1bde04c8d1d4ffa2bb57154371ef2df0) openCompleteCallback,void * userContextCallback)**

Opens connection to IoTHub.

#### Parameters
* `messagingClientHandle` The handle created by a call to the create function. 

* `openCompleteCallback` The callback specified by the user for receiving confirmation of the connection opened. The user can specify a `NULL` value here to indicate that no callback is required. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

#### Returns
IOTHUB_MESSAGING_OK upon success or an error code upon failure.

