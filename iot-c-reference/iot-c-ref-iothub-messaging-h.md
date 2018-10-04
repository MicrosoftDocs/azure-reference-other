# Header file iothub_messaging.h 

Stub comment for brief. Please update this comment.

## Includes

\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include ["iothub_messaging_ll.h"](iot-c-ref-iothub-messaging-ll-h.md)  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IoTHubMessaging_Create](./iot-c-ref-iothub-messaging-h/iothubmessaging-create.md)            | Creates a IoT Hub Service Client Messaging handle for use it in consequent APIs.
[IoTHubMessaging_Destroy](./iot-c-ref-iothub-messaging-h/iothubmessaging-destroy.md)            | Disposes of resources allocated by the IoT Hub Service Client Messaging.
[IoTHubMessaging_Open](./iot-c-ref-iothub-messaging-h/iothubmessaging-open.md)            | Opens connection to IoTHub.
[IoTHubMessaging_Close](./iot-c-ref-iothub-messaging-h/iothubmessaging-close.md)            | Closes connection to IoTHub.
[IoTHubMessaging_SendAsync](./iot-c-ref-iothub-messaging-h/iothubmessaging-sendasync.md)            | Asynchronous call to send the message to a specified device.
[IoTHubMessaging_SetFeedbackMessageCallback](./iot-c-ref-iothub-messaging-h/iothubmessaging-setfeedbackmessagecallback.md)            | This API specifies a callback to be used when the device receives the message.
[IoTHubMessaging_SetTrustedCert](./iot-c-ref-iothub-messaging-h/iothubmessaging-settrustedcert.md)            | This function is meant to be called by the user when to set the trusted certificate on the tls connection.

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
IOTHUB_MESSAGING_CLIENT_HANDLE            | 

## Function documentation

#### IoTHubMessaging_Create 
[IOTHUB_MESSAGING_CLIENT_HANDLE](#iothub__messaging_8h_1a388e756ded834589f37bbd04bf9cc9c0) [IoTHubMessaging_Create](#iothub__messaging_8h_1a46b00baeeb17c30bcdce5b3680c1fda3)([IOTHUB_SERVICE_CLIENT_AUTH_HANDLE](#iothub__service__client__auth_8h_1a47d2f6357931c33108eb9fba95d8730b) serviceClientHandle)

#### IoTHubMessaging_Destroy 
void [IoTHubMessaging_Destroy](#iothub__messaging_8h_1a5714171907353034b3bc60b7a404fc79)([IOTHUB_MESSAGING_CLIENT_HANDLE](#iothub__messaging_8h_1a388e756ded834589f37bbd04bf9cc9c0) messagingClientHandle)

#### IoTHubMessaging_Open 
[IOTHUB_MESSAGING_RESULT](#iothub__messaging__ll_8h_1ac5ac4fdc87db94cc7ddb7773e79290cd) [IoTHubMessaging_Open](#iothub__messaging_8h_1a8844eceec74a77fc647c83d134e873ef)([IOTHUB_MESSAGING_CLIENT_HANDLE](#iothub__messaging_8h_1a388e756ded834589f37bbd04bf9cc9c0) messagingClientHandle,[IOTHUB_OPEN_COMPLETE_CALLBACK](#iothub__messaging__ll_8h_1a1bde04c8d1d4ffa2bb57154371ef2df0) openCompleteCallback,void * userContextCallback)

#### IoTHubMessaging_Close 
void [IoTHubMessaging_Close](#iothub__messaging_8h_1a5642fd8ed79c97ee88713fcec150cca0)([IOTHUB_MESSAGING_CLIENT_HANDLE](#iothub__messaging_8h_1a388e756ded834589f37bbd04bf9cc9c0) messagingClientHandle)

#### IoTHubMessaging_SendAsync 
[IOTHUB_MESSAGING_RESULT](#iothub__messaging__ll_8h_1ac5ac4fdc87db94cc7ddb7773e79290cd) [IoTHubMessaging_SendAsync](#iothub__messaging_8h_1a4393926997e036da151cc2ec2668f4b1)([IOTHUB_MESSAGING_CLIENT_HANDLE](#iothub__messaging_8h_1a388e756ded834589f37bbd04bf9cc9c0) messagingClientHandle,const char * deviceId,[IOTHUB_MESSAGE_HANDLE](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) message,[IOTHUB_SEND_COMPLETE_CALLBACK](#iothub__messaging__ll_8h_1a47509c33cdd854fc209df239dcaef5a9) sendCompleteCallback,void * userContextCallback)

#### IoTHubMessaging_SetFeedbackMessageCallback 
[IOTHUB_MESSAGING_RESULT](#iothub__messaging__ll_8h_1ac5ac4fdc87db94cc7ddb7773e79290cd) [IoTHubMessaging_SetFeedbackMessageCallback](#iothub__messaging_8h_1a6c2c543c623b2bf45c6de7c2f6b07540)([IOTHUB_MESSAGING_CLIENT_HANDLE](#iothub__messaging_8h_1a388e756ded834589f37bbd04bf9cc9c0) messagingClientHandle,[IOTHUB_FEEDBACK_MESSAGE_RECEIVED_CALLBACK](#iothub__messaging__ll_8h_1a323b2eb492755a62424f130c7cb75888) feedbackMessageReceivedCallback,void * userContextCallback)

#### IoTHubMessaging_SetTrustedCert 
[IOTHUB_MESSAGING_RESULT](#iothub__messaging__ll_8h_1ac5ac4fdc87db94cc7ddb7773e79290cd) [IoTHubMessaging_SetTrustedCert](#iothub__messaging_8h_1ae097c37e0046bb193c1e14dd8c8434be)([IOTHUB_MESSAGING_CLIENT_HANDLE](#iothub__messaging_8h_1a388e756ded834589f37bbd04bf9cc9c0) messagingClientHandle,const char * trusted_cert)

