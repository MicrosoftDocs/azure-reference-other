# IoTHubMessaging_SendAsync()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging.h"](../iot-c-ref-iothub-messaging-h.md)  

## Syntax

```C
IOTHUB_MESSAGING_RESULT IoTHubMessaging_SendAsync(
  IOTHUB_MESSAGING_CLIENT_HANDLE  	messagingClientHandle,
  const char *                    	deviceId,
  IOTHUB_MESSAGE_HANDLE           	message,
  IOTHUB_SEND_COMPLETE_CALLBACK   	sendCompleteCallback,
  void *                          	userContextCallback
);

```

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

