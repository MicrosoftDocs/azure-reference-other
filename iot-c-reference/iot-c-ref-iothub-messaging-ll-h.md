# Header file iothub_messaging_ll.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/crt_abstractions.h"  
\#include ["azure_c_shared_utility/singlylinkedlist.h"](iot-c-ref-singlylinkedlist-h.md)  
\#include ["azure_c_shared_utility/map.h"](iot-c-ref-map-h.md)  
\#include ["iothub_message.h"](iot-c-ref-iothub-message-h.md)  
\#include ["iothub_service_client_auth.h"](iot-c-ref-iothub-service-client-auth-h.md)  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IOTHUB_FEEDBACK_STATUS_CODEStrings](./iot-c-ref-iothub-messaging-ll-h/iothub-feedback-status-codestrings.md)            | 
[IOTHUB_FEEDBACK_STATUS_CODE_FromString](./iot-c-ref-iothub-messaging-ll-h/iothub-feedback-status-code-fromstring.md)            | 
[IOTHUB_MESSAGE_SEND_STATEStrings](./iot-c-ref-iothub-messaging-ll-h/iothub-message-send-statestrings.md)            | 
[IOTHUB_MESSAGE_SEND_STATE_FromString](./iot-c-ref-iothub-messaging-ll-h/iothub-message-send-state-fromstring.md)            | 
[IOTHUB_MESSAGING_RESULTStrings](./iot-c-ref-iothub-messaging-ll-h/iothub-messaging-resultstrings.md)            | 
[IOTHUB_MESSAGING_RESULT_FromString](./iot-c-ref-iothub-messaging-ll-h/iothub-messaging-result-fromstring.md)            | 
[IoTHubMessaging_LL_Create](./iot-c-ref-iothub-messaging-ll-h/iothubmessaging-ll-create.md)            | Creates a IoT Hub Service Client Messaging handle for use it in consequent APIs.
[IoTHubMessaging_LL_Destroy](./iot-c-ref-iothub-messaging-ll-h/iothubmessaging-ll-destroy.md)            | Disposes of resources allocated by the IoT Hub Service Client Messaging.
[IoTHubMessaging_LL_Open](./iot-c-ref-iothub-messaging-ll-h/iothubmessaging-ll-open.md)            | Opens connection to IoTHub.
[IoTHubMessaging_LL_Close](./iot-c-ref-iothub-messaging-ll-h/iothubmessaging-ll-close.md)            | Closes connection to IoTHub.
[IoTHubMessaging_LL_Send](./iot-c-ref-iothub-messaging-ll-h/iothubmessaging-ll-send.md)            | Synchronous call to send the message to a specified device.
[IoTHubMessaging_LL_SetFeedbackMessageCallback](./iot-c-ref-iothub-messaging-ll-h/iothubmessaging-ll-setfeedbackmessagecallback.md)            | This API specifies a callback to be used when the device receives the message.
[IoTHubMessaging_LL_DoWork](./iot-c-ref-iothub-messaging-ll-h/iothubmessaging-ll-dowork.md)            | This function is meant to be called by the user when work (sending/receiving) can be done by the IoTHubServiceClient.
[IoTHubMessaging_LL_SetTrustedCert](./iot-c-ref-iothub-messaging-ll-h/iothubmessaging-ll-settrustedcert.md)            | This function is meant to be called by the user when to set the trusted certificate on the tls connection.

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IOTHUB_FEEDBACK_STATUS_CODE_VALUES            | 
IOTHUB_MESSAGE_SEND_STATE_VALUES            | 
IOTHUB_MESSAGING_RESULT_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
IOTHUB_MESSAGING_HANDLE            | 
IOTHUB_OPEN_COMPLETE_CALLBACK            | 
IOTHUB_SEND_COMPLETE_CALLBACK            | 
IOTHUB_FEEDBACK_MESSAGE_RECEIVED_CALLBACK            | 

## Function documentation

#### IOTHUB_FEEDBACK_STATUS_CODEStrings 
const char * [IOTHUB_FEEDBACK_STATUS_CODEStrings](#iothub__messaging__ll_8h_1a36f7d7cbd26045dea5ee0862ac26e391)([IOTHUB_FEEDBACK_STATUS_CODE](#iothub__messaging__ll_8h_1a5b57127ee43a2e8919c3f8225c628498) value)

#### IOTHUB_FEEDBACK_STATUS_CODE_FromString 
int [IOTHUB_FEEDBACK_STATUS_CODE_FromString](#iothub__messaging__ll_8h_1aa0665eb9699519467a1c17d42ce632f1)(const char * enumAsString,[IOTHUB_FEEDBACK_STATUS_CODE](#iothub__messaging__ll_8h_1a5b57127ee43a2e8919c3f8225c628498) * destination)

#### IOTHUB_MESSAGE_SEND_STATEStrings 
const char * [IOTHUB_MESSAGE_SEND_STATEStrings](#iothub__messaging__ll_8h_1a1b2b5b8e31269892b73fb8f82926de4f)([IOTHUB_MESSAGE_SEND_STATE](#iothub__messaging__ll_8h_1a46b779019d8b82c8aa5631b865853cc0) value)

#### IOTHUB_MESSAGE_SEND_STATE_FromString 
int [IOTHUB_MESSAGE_SEND_STATE_FromString](#iothub__messaging__ll_8h_1a6938a327a68abdb7c05a250cac3fa76c)(const char * enumAsString,[IOTHUB_MESSAGE_SEND_STATE](#iothub__messaging__ll_8h_1a46b779019d8b82c8aa5631b865853cc0) * destination)

#### IOTHUB_MESSAGING_RESULTStrings 
const char * [IOTHUB_MESSAGING_RESULTStrings](#iothub__messaging__ll_8h_1ac391a9d597a3c8127d8a48056c753820)([IOTHUB_MESSAGING_RESULT](#iothub__messaging__ll_8h_1ac5ac4fdc87db94cc7ddb7773e79290cd) value)

#### IOTHUB_MESSAGING_RESULT_FromString 
int [IOTHUB_MESSAGING_RESULT_FromString](#iothub__messaging__ll_8h_1aa3282c3b418a8cf0ef48467826c8a32f)(const char * enumAsString,[IOTHUB_MESSAGING_RESULT](#iothub__messaging__ll_8h_1ac5ac4fdc87db94cc7ddb7773e79290cd) * destination)

#### IoTHubMessaging_LL_Create 
[IOTHUB_MESSAGING_HANDLE](#iothub__messaging__ll_8h_1ad4dd5cf65fd836ab5b053d59148343ff) [IoTHubMessaging_LL_Create](#iothub__messaging__ll_8h_1a5b087a9084627857a9242ca56afbc056)([IOTHUB_SERVICE_CLIENT_AUTH_HANDLE](#iothub__service__client__auth_8h_1a47d2f6357931c33108eb9fba95d8730b) iotHubMessagingServiceClientHandle)

#### IoTHubMessaging_LL_Destroy 
void [IoTHubMessaging_LL_Destroy](#iothub__messaging__ll_8h_1a16023104ba14725b6648b1694d208ab3)([IOTHUB_MESSAGING_HANDLE](#iothub__messaging__ll_8h_1ad4dd5cf65fd836ab5b053d59148343ff) messagingHandle)

#### IoTHubMessaging_LL_Open 
[IOTHUB_MESSAGING_RESULT](#iothub__messaging__ll_8h_1ac5ac4fdc87db94cc7ddb7773e79290cd) [IoTHubMessaging_LL_Open](#iothub__messaging__ll_8h_1a6d040cb826b161bf3187bfec7448b395)([IOTHUB_MESSAGING_HANDLE](#iothub__messaging__ll_8h_1ad4dd5cf65fd836ab5b053d59148343ff) messagingHandle,[IOTHUB_OPEN_COMPLETE_CALLBACK](#iothub__messaging__ll_8h_1a1bde04c8d1d4ffa2bb57154371ef2df0) openCompleteCallback,void * userContextCallback)

#### IoTHubMessaging_LL_Close 
void [IoTHubMessaging_LL_Close](#iothub__messaging__ll_8h_1a6b271168ba34cad1dcc380f338c59c12)([IOTHUB_MESSAGING_HANDLE](#iothub__messaging__ll_8h_1ad4dd5cf65fd836ab5b053d59148343ff) messagingHandle)

#### IoTHubMessaging_LL_Send 
[IOTHUB_MESSAGING_RESULT](#iothub__messaging__ll_8h_1ac5ac4fdc87db94cc7ddb7773e79290cd) [IoTHubMessaging_LL_Send](#iothub__messaging__ll_8h_1a331f5c5ac032ac2b38b1025b80cba15d)([IOTHUB_MESSAGING_HANDLE](#iothub__messaging__ll_8h_1ad4dd5cf65fd836ab5b053d59148343ff) messagingHandle,const char * deviceId,[IOTHUB_MESSAGE_HANDLE](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) message,[IOTHUB_SEND_COMPLETE_CALLBACK](#iothub__messaging__ll_8h_1a47509c33cdd854fc209df239dcaef5a9) sendCompleteCallback,void * userContextCallback)

#### IoTHubMessaging_LL_SetFeedbackMessageCallback 
[IOTHUB_MESSAGING_RESULT](#iothub__messaging__ll_8h_1ac5ac4fdc87db94cc7ddb7773e79290cd) [IoTHubMessaging_LL_SetFeedbackMessageCallback](#iothub__messaging__ll_8h_1a47226ad75e5373096c1783125ceb0f81)([IOTHUB_MESSAGING_HANDLE](#iothub__messaging__ll_8h_1ad4dd5cf65fd836ab5b053d59148343ff) messagingHandle,[IOTHUB_FEEDBACK_MESSAGE_RECEIVED_CALLBACK](#iothub__messaging__ll_8h_1a323b2eb492755a62424f130c7cb75888) feedbackMessageReceivedCallback,void * userContextCallback)

#### IoTHubMessaging_LL_DoWork 
void [IoTHubMessaging_LL_DoWork](#iothub__messaging__ll_8h_1ad83618f43c1309edae5ab92f58abd4b5)([IOTHUB_MESSAGING_HANDLE](#iothub__messaging__ll_8h_1ad4dd5cf65fd836ab5b053d59148343ff) messagingHandle)

#### IoTHubMessaging_LL_SetTrustedCert 
[IOTHUB_MESSAGING_RESULT](#iothub__messaging__ll_8h_1ac5ac4fdc87db94cc7ddb7773e79290cd) [IoTHubMessaging_LL_SetTrustedCert](#iothub__messaging__ll_8h_1a137346dac27148c3055f798b3be72cf2)([IOTHUB_MESSAGING_HANDLE](#iothub__messaging__ll_8h_1ad4dd5cf65fd836ab5b053d59148343ff) messagingHandle,const char * trusted_cert)

