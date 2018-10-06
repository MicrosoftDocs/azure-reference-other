# iothub_messaging_ll.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/crt_abstractions.h"  
\#include "[azure_c_shared_utility/singlylinkedlist.h](iot-c-ref-singlylinkedlist-h.md)"  
\#include "[azure_c_shared_utility/map.h](iot-c-ref-map-h.md)"  
\#include "[iothub_message.h](iot-c-ref-iothub-message-h.md)"  
\#include "[iothub_service_client_auth.h](iot-c-ref-iothub-service-client-auth-h.md)"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  

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

## Structures

#### IOTHUB_SERVICE_FEEDBACK_RECORD

```C
struct IOTHUB_SERVICE_FEEDBACK_RECORD {
  char *                                                                                                                                                                                                                                                                                                                                               description,
  const char *                                                                                                                                                                                                                                                                                                                                         deviceId,
  const char *                                                                                                                                                                                                                                                                                                                                         correlationId,
  const char *                                                                                                                                                                                                                                                                                                                                         generationId,
  const char *                                                                                                                                                                                                                                                                                                                                         enqueuedTimeUtc,
  [IOTHUB_FEEDBACK_STATUS_CODE](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    })  statusCode,
  const char *                                                                                                                                                                                                                                                                                                                                         originalMessageId
};
```
Member name                 | Description                                
----------------------------|----------------
 description            | 
 deviceId            | 
 correlationId            | 
 generationId            | 
 enqueuedTimeUtc            | 
 statusCode            | 
 originalMessageId            | 
#### IOTHUB_SERVICE_FEEDBACK_BATCH

```C
struct IOTHUB_SERVICE_FEEDBACK_BATCH {
  const char *                                                                                                                                                                                                                                                                                                                                     userId,
  const char *                                                                                                                                                                                                                                                                                                                                     lockToken,
  [SINGLYLINKEDLIST_HANDLE](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    })  feedbackRecordList
};
```
Member name                 | Description                                
----------------------------|----------------
 userId            | 
 lockToken            | 
 feedbackRecordList            | 

## Macro definitions

#### IOTHUB_FEEDBACK_STATUS_CODE_VALUES

```C
#define IOTHUB_FEEDBACK_STATUS_CODE_VALUES \
 IOTHUB_FEEDBACK_STATUS_CODE_SUCCESS, \
 IOTHUB_FEEDBACK_STATUS_CODE_EXPIRED, \
 IOTHUB_FEEDBACK_STATUS_CODE_DELIVER_COUNT_EXCEEDED, \
 IOTHUB_FEEDBACK_STATUS_CODE_REJECTED, \
 IOTHUB_FEEDBACK_STATUS_CODE_UNKNOWN 

```

#### IOTHUB_MESSAGE_SEND_STATE_VALUES

```C
#define IOTHUB_MESSAGE_SEND_STATE_VALUES \
 IOTHUB_MESSAGE_SEND_STATE_NOT_SENT, \
 IOTHUB_MESSAGE_SEND_STATE_SEND_IN_PROGRESS, \
 IOTHUB_MESSAGE_SEND_STATE_SENT_OK, \
 IOTHUB_MESSAGE_SEND_STATE_SEND_FAILED 

```

#### IOTHUB_MESSAGING_RESULT_VALUES

```C
#define IOTHUB_MESSAGING_RESULT_VALUES \
 IOTHUB_MESSAGING_OK, \
 IOTHUB_MESSAGING_INVALID_ARG, \
 IOTHUB_MESSAGING_ERROR, \
 IOTHUB_MESSAGING_INVALID_JSON, \
 IOTHUB_MESSAGING_DEVICE_EXIST, \
 IOTHUB_MESSAGING_CALLBACK_NOT_SET 

```

## Enumeration types

#### IOTHUB_FEEDBACK_STATUS_CODE

```C
enum IOTHUB_FEEDBACK_STATUS_CODE {
  IOTHUB_FEEDBACK_STATUS_CODE_SUCCESS,
  IOTHUB_FEEDBACK_STATUS_CODE_EXPIRED,
  IOTHUB_FEEDBACK_STATUS_CODE_DELIVER_COUNT_EXCEEDED,
  IOTHUB_FEEDBACK_STATUS_CODE_REJECTED,
  IOTHUB_FEEDBACK_STATUS_CODE_UNKNOWN
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUB_FEEDBACK_STATUS_CODE_SUCCESS            | 
 IOTHUB_FEEDBACK_STATUS_CODE_EXPIRED            | 
 IOTHUB_FEEDBACK_STATUS_CODE_DELIVER_COUNT_EXCEEDED            | 
 IOTHUB_FEEDBACK_STATUS_CODE_REJECTED            | 
 IOTHUB_FEEDBACK_STATUS_CODE_UNKNOWN            | 

#### IOTHUB_MESSAGE_SEND_STATE

```C
enum IOTHUB_MESSAGE_SEND_STATE {
  IOTHUB_MESSAGE_SEND_STATE_NOT_SENT,
  IOTHUB_MESSAGE_SEND_STATE_SEND_IN_PROGRESS,
  IOTHUB_MESSAGE_SEND_STATE_SENT_OK,
  IOTHUB_MESSAGE_SEND_STATE_SEND_FAILED
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUB_MESSAGE_SEND_STATE_NOT_SENT            | 
 IOTHUB_MESSAGE_SEND_STATE_SEND_IN_PROGRESS            | 
 IOTHUB_MESSAGE_SEND_STATE_SENT_OK            | 
 IOTHUB_MESSAGE_SEND_STATE_SEND_FAILED            | 

#### IOTHUB_MESSAGING_RESULT

```C
enum IOTHUB_MESSAGING_RESULT {
  IOTHUB_MESSAGING_OK,
  IOTHUB_MESSAGING_INVALID_ARG,
  IOTHUB_MESSAGING_ERROR,
  IOTHUB_MESSAGING_INVALID_JSON,
  IOTHUB_MESSAGING_DEVICE_EXIST,
  IOTHUB_MESSAGING_CALLBACK_NOT_SET
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUB_MESSAGING_OK            | 
 IOTHUB_MESSAGING_INVALID_ARG            | 
 IOTHUB_MESSAGING_ERROR            | 
 IOTHUB_MESSAGING_INVALID_JSON            | 
 IOTHUB_MESSAGING_DEVICE_EXIST            | 
 IOTHUB_MESSAGING_CALLBACK_NOT_SET            | 

