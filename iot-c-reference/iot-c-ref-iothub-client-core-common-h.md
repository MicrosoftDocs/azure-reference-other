# iothub_client_core_common.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "[iothub_transport_ll.h](iot-c-ref-iothub-transport-ll-h.md)"  
\#include "[iothub_message.h](iot-c-ref-iothub-message-h.md)"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IOTHUB_CLIENT_FILE_UPLOAD_RESULTStrings](./iot-c-ref-iothub-client-core-common-h/iothub-client-file-upload-resultstrings.md)            | 
[IOTHUB_CLIENT_FILE_UPLOAD_RESULT_FromString](./iot-c-ref-iothub-client-core-common-h/iothub-client-file-upload-result-fromstring.md)            | 
[IOTHUB_CLIENT_RESULTStrings](./iot-c-ref-iothub-client-core-common-h/iothub-client-resultstrings.md)            | 
[IOTHUB_CLIENT_RESULT_FromString](./iot-c-ref-iothub-client-core-common-h/iothub-client-result-fromstring.md)            | 
[IOTHUB_CLIENT_RETRY_POLICYStrings](./iot-c-ref-iothub-client-core-common-h/iothub-client-retry-policystrings.md)            | 
[IOTHUB_CLIENT_RETRY_POLICY_FromString](./iot-c-ref-iothub-client-core-common-h/iothub-client-retry-policy-fromstring.md)            | 
[IOTHUB_CLIENT_STATUSStrings](./iot-c-ref-iothub-client-core-common-h/iothub-client-statusstrings.md)            | 
[IOTHUB_CLIENT_STATUS_FromString](./iot-c-ref-iothub-client-core-common-h/iothub-client-status-fromstring.md)            | 
[IOTHUB_IDENTITY_TYPEStrings](./iot-c-ref-iothub-client-core-common-h/iothub-identity-typestrings.md)            | 
[IOTHUB_IDENTITY_TYPE_FromString](./iot-c-ref-iothub-client-core-common-h/iothub-identity-type-fromstring.md)            | 
[IOTHUB_PROCESS_ITEM_RESULTStrings](./iot-c-ref-iothub-client-core-common-h/iothub-process-item-resultstrings.md)            | 
[IOTHUB_PROCESS_ITEM_RESULT_FromString](./iot-c-ref-iothub-client-core-common-h/iothub-process-item-result-fromstring.md)            | 
[IOTHUBMESSAGE_DISPOSITION_RESULTStrings](./iot-c-ref-iothub-client-core-common-h/iothubmessage-disposition-resultstrings.md)            | 
[IOTHUBMESSAGE_DISPOSITION_RESULT_FromString](./iot-c-ref-iothub-client-core-common-h/iothubmessage-disposition-result-fromstring.md)            | 
[IOTHUB_CLIENT_IOTHUB_METHOD_STATUSStrings](./iot-c-ref-iothub-client-core-common-h/iothub-client-iothub-method-statusstrings.md)            | 
[IOTHUB_CLIENT_IOTHUB_METHOD_STATUS_FromString](./iot-c-ref-iothub-client-core-common-h/iothub-client-iothub-method-status-fromstring.md)            | 
[IOTHUB_CLIENT_CONFIRMATION_RESULTStrings](./iot-c-ref-iothub-client-core-common-h/iothub-client-confirmation-resultstrings.md)            | 
[IOTHUB_CLIENT_CONFIRMATION_RESULT_FromString](./iot-c-ref-iothub-client-core-common-h/iothub-client-confirmation-result-fromstring.md)            | 
[IOTHUB_CLIENT_CONNECTION_STATUSStrings](./iot-c-ref-iothub-client-core-common-h/iothub-client-connection-statusstrings.md)            | 
[IOTHUB_CLIENT_CONNECTION_STATUS_FromString](./iot-c-ref-iothub-client-core-common-h/iothub-client-connection-status-fromstring.md)            | 
[IOTHUB_CLIENT_CONNECTION_STATUS_REASONStrings](./iot-c-ref-iothub-client-core-common-h/iothub-client-connection-status-reasonstrings.md)            | 
[IOTHUB_CLIENT_CONNECTION_STATUS_REASON_FromString](./iot-c-ref-iothub-client-core-common-h/iothub-client-connection-status-reason-fromstring.md)            | 
[TRANSPORT_TYPEStrings](./iot-c-ref-iothub-client-core-common-h/transport-typestrings.md)            | 
[TRANSPORT_TYPE_FromString](./iot-c-ref-iothub-client-core-common-h/transport-type-fromstring.md)            | 
[DEVICE_TWIN_UPDATE_STATEStrings](./iot-c-ref-iothub-client-core-common-h/device-twin-update-statestrings.md)            | 
[DEVICE_TWIN_UPDATE_STATE_FromString](./iot-c-ref-iothub-client-core-common-h/device-twin-update-state-fromstring.md)            | 
[IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_RESULTStrings](./iot-c-ref-iothub-client-core-common-h/iothub-client-file-upload-get-data-resultstrings.md)            | 
[IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_RESULT_FromString](./iot-c-ref-iothub-client-core-common-h/iothub-client-file-upload-get-data-result-fromstring.md)            | 

## Structures

#### IOTHUB_CLIENT_CONFIG

```C
struct IOTHUB_CLIENT_CONFIG {
  [IOTHUB_CLIENT_TRANSPORT_PROVIDER](#undefined)  protocol,
  const char *                                    deviceId,
  const char *                                    deviceKey,
  const char *                                    deviceSasToken,
  const char *                                    iotHubName,
  const char *                                    iotHubSuffix,
  const char *                                    protocolGatewayHostName
};
```
Member name                 | Description                                
----------------------------|----------------
 protocol            | A function pointer that is passed into the `IoTHubClientCreate`. A function definition for AMQP is defined in the include `[iothubtransportamqp.h](#undefined)`. A function definition for HTTP is defined in the include `[iothubtransporthttp.h](#undefined)` A function definition for MQTT is defined in the include `[iothubtransportmqtt.h](#undefined)`. 

 deviceId            | A string that identifies the device. 

 deviceKey            | The device key used to authenticate the device. If neither deviceSasToken nor deviceKey is present then the authentication is assumed x509. 

 deviceSasToken            | The device SAS Token used to authenticate the device in place of device key. If neither deviceSasToken nor deviceKey is present then the authentication is assumed x509. 

 iotHubName            | The IoT Hub name to which the device is connecting. 

 iotHubSuffix            | IoT Hub suffix goes here, e.g., private.azure-devices-int.net. 

 protocolGatewayHostName            | 
#### IOTHUB_CLIENT_DEVICE_CONFIG

```C
struct IOTHUB_CLIENT_DEVICE_CONFIG {
  [IOTHUB_CLIENT_TRANSPORT_PROVIDER](#undefined)  protocol,
  void *                                          transportHandle,
  const char *                                    deviceId,
  const char *                                    deviceKey,
  const char *                                    deviceSasToken
};
```
Member name                 | Description                                
----------------------------|----------------
 protocol            | A function pointer that is passed into the `IoTHubClientCreate`. A function definition for AMQP is defined in the include `[iothubtransportamqp.h](#undefined)`. A function definition for HTTP is defined in the include `[iothubtransporthttp.h](#undefined)` A function definition for MQTT is defined in the include `[iothubtransportmqtt.h](#undefined)`. 

 transportHandle            | a transport handle implementing the protocol 

 deviceId            | A string that identifies the device. 

 deviceKey            | The device key used to authenticate the device. x509 authentication is is not supported for multiplexed connections. 

 deviceSasToken            | The device SAS Token used to authenticate the device in place of device key. x509 authentication is is not supported for multiplexed connections. 

## Macro definitions

#### IOTHUB_CLIENT_FILE_UPLOAD_RESULT_VALUES

```C
#define IOTHUB_CLIENT_FILE_UPLOAD_RESULT_VALUES \
 FILE_UPLOAD_OK, \
 FILE_UPLOAD_ERROR 

```

#### IOTHUB_CLIENT_RESULT_VALUES

```C
#define IOTHUB_CLIENT_RESULT_VALUES \
 IOTHUB_CLIENT_OK, \
 IOTHUB_CLIENT_INVALID_ARG, \
 IOTHUB_CLIENT_ERROR, \
 IOTHUB_CLIENT_INVALID_SIZE, \
 IOTHUB_CLIENT_INDEFINITE_TIME 

```

#### IOTHUB_CLIENT_RETRY_POLICY_VALUES

```C
#define IOTHUB_CLIENT_RETRY_POLICY_VALUES \
 IOTHUB_CLIENT_RETRY_NONE, \
 IOTHUB_CLIENT_RETRY_IMMEDIATE, \
 IOTHUB_CLIENT_RETRY_INTERVAL, \
 IOTHUB_CLIENT_RETRY_LINEAR_BACKOFF, \
 IOTHUB_CLIENT_RETRY_EXPONENTIAL_BACKOFF, \
 IOTHUB_CLIENT_RETRY_EXPONENTIAL_BACKOFF_WITH_JITTER, \
 IOTHUB_CLIENT_RETRY_RANDOM 

```

#### IOTHUB_CLIENT_STATUS_VALUES

```C
#define IOTHUB_CLIENT_STATUS_VALUES \
 IOTHUB_CLIENT_SEND_STATUS_IDLE, \
 IOTHUB_CLIENT_SEND_STATUS_BUSY 

```

#### IOTHUB_IDENTITY_TYPE_VALUE

```C
#define IOTHUB_IDENTITY_TYPE_VALUE \
 IOTHUB_TYPE_TELEMETRY, \
 IOTHUB_TYPE_DEVICE_TWIN, \
 IOTHUB_TYPE_DEVICE_METHODS, \
 IOTHUB_TYPE_EVENT_QUEUE 

```

#### IOTHUB_PROCESS_ITEM_RESULT_VALUE

```C
#define IOTHUB_PROCESS_ITEM_RESULT_VALUE \
 IOTHUB_PROCESS_OK, \
 IOTHUB_PROCESS_ERROR, \
 IOTHUB_PROCESS_NOT_CONNECTED, \
 IOTHUB_PROCESS_CONTINUE 

```

#### IOTHUBMESSAGE_DISPOSITION_RESULT_VALUES

```C
#define IOTHUBMESSAGE_DISPOSITION_RESULT_VALUES \
 IOTHUBMESSAGE_ACCEPTED, \
 IOTHUBMESSAGE_REJECTED, \
 IOTHUBMESSAGE_ABANDONED 

```

#### IOTHUB_CLIENT_IOTHUB_METHOD_STATUS_VALUES

```C
#define IOTHUB_CLIENT_IOTHUB_METHOD_STATUS_VALUES \
 IOTHUB_CLIENT_IOTHUB_METHOD_STATUS_SUCCESS, \
 IOTHUB_CLIENT_IOTHUB_METHOD_STATUS_ERROR 

```

#### IOTHUB_CLIENT_CONFIRMATION_RESULT_VALUES

```C
#define IOTHUB_CLIENT_CONFIRMATION_RESULT_VALUES \
 IOTHUB_CLIENT_CONFIRMATION_OK, \
 IOTHUB_CLIENT_CONFIRMATION_BECAUSE_DESTROY, \
 IOTHUB_CLIENT_CONFIRMATION_MESSAGE_TIMEOUT, \
 IOTHUB_CLIENT_CONFIRMATION_ERROR 

```

#### IOTHUB_CLIENT_CONNECTION_STATUS_VALUES

```C
#define IOTHUB_CLIENT_CONNECTION_STATUS_VALUES \
 IOTHUB_CLIENT_CONNECTION_AUTHENTICATED, \
 IOTHUB_CLIENT_CONNECTION_UNAUTHENTICATED 

```

#### IOTHUB_CLIENT_CONNECTION_STATUS_REASON_VALUES

```C
#define IOTHUB_CLIENT_CONNECTION_STATUS_REASON_VALUES \
 IOTHUB_CLIENT_CONNECTION_EXPIRED_SAS_TOKEN, \
 IOTHUB_CLIENT_CONNECTION_DEVICE_DISABLED, \
 IOTHUB_CLIENT_CONNECTION_BAD_CREDENTIAL, \
 IOTHUB_CLIENT_CONNECTION_RETRY_EXPIRED, \
 IOTHUB_CLIENT_CONNECTION_NO_NETWORK, \
 IOTHUB_CLIENT_CONNECTION_COMMUNICATION_ERROR, \
 IOTHUB_CLIENT_CONNECTION_OK 

```

#### TRANSPORT_TYPE_VALUES

```C
#define TRANSPORT_TYPE_VALUES TRANSPORT_LL 

```

#### DEVICE_TWIN_UPDATE_STATE_VALUES

```C
#define DEVICE_TWIN_UPDATE_STATE_VALUES \
 DEVICE_TWIN_UPDATE_COMPLETE, \
 DEVICE_TWIN_UPDATE_PARTIAL 

```

#### IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_RESULT_VALUES

```C
#define IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_RESULT_VALUES \
 IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_OK, \
 IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_ABORT 

```

## Enumeration types

#### IOTHUB_CLIENT_FILE_UPLOAD_RESULT

```C
enum IOTHUB_CLIENT_FILE_UPLOAD_RESULT {
  FILE_UPLOAD_OK,
  FILE_UPLOAD_ERROR
}

```
Constant                    | Description                                
----------------------------|----------------
 FILE_UPLOAD_OK            | 
 FILE_UPLOAD_ERROR            | 

#### IOTHUB_CLIENT_RESULT

Enumeration specifying the status of calls to various APIs in this module. 

```C
enum IOTHUB_CLIENT_RESULT {
  IOTHUB_CLIENT_OK,
  IOTHUB_CLIENT_INVALID_ARG,
  IOTHUB_CLIENT_ERROR,
  IOTHUB_CLIENT_INVALID_SIZE,
  IOTHUB_CLIENT_INDEFINITE_TIME
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUB_CLIENT_OK            | 
 IOTHUB_CLIENT_INVALID_ARG            | 
 IOTHUB_CLIENT_ERROR            | 
 IOTHUB_CLIENT_INVALID_SIZE            | 
 IOTHUB_CLIENT_INDEFINITE_TIME            | 

#### IOTHUB_CLIENT_RETRY_POLICY

Enumeration passed in by the IoT Hub when the event confirmation callback is invoked to indicate status of the event processing in the hub. 

```C
enum IOTHUB_CLIENT_RETRY_POLICY {
  IOTHUB_CLIENT_RETRY_NONE,
  IOTHUB_CLIENT_RETRY_IMMEDIATE,
  IOTHUB_CLIENT_RETRY_INTERVAL,
  IOTHUB_CLIENT_RETRY_LINEAR_BACKOFF,
  IOTHUB_CLIENT_RETRY_EXPONENTIAL_BACKOFF,
  IOTHUB_CLIENT_RETRY_EXPONENTIAL_BACKOFF_WITH_JITTER,
  IOTHUB_CLIENT_RETRY_RANDOM
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUB_CLIENT_RETRY_NONE            | 
 IOTHUB_CLIENT_RETRY_IMMEDIATE            | 
 IOTHUB_CLIENT_RETRY_INTERVAL            | 
 IOTHUB_CLIENT_RETRY_LINEAR_BACKOFF            | 
 IOTHUB_CLIENT_RETRY_EXPONENTIAL_BACKOFF            | 
 IOTHUB_CLIENT_RETRY_EXPONENTIAL_BACKOFF_WITH_JITTER            | 
 IOTHUB_CLIENT_RETRY_RANDOM            | 

#### IOTHUB_CLIENT_STATUS

Enumeration returned by the [IoTHubClient_LL_GetSendStatus](#undefined) API to indicate the current sending status of the IoT Hub client. 

```C
enum IOTHUB_CLIENT_STATUS {
  IOTHUB_CLIENT_SEND_STATUS_IDLE,
  IOTHUB_CLIENT_SEND_STATUS_BUSY
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUB_CLIENT_SEND_STATUS_IDLE            | 
 IOTHUB_CLIENT_SEND_STATUS_BUSY            | 

#### IOTHUB_IDENTITY_TYPE

```C
enum IOTHUB_IDENTITY_TYPE {
  IOTHUB_TYPE_TELEMETRY,
  IOTHUB_TYPE_DEVICE_TWIN,
  IOTHUB_TYPE_DEVICE_METHODS,
  IOTHUB_TYPE_EVENT_QUEUE
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUB_TYPE_TELEMETRY            | 
 IOTHUB_TYPE_DEVICE_TWIN            | 
 IOTHUB_TYPE_DEVICE_METHODS            | 
 IOTHUB_TYPE_EVENT_QUEUE            | 

#### IOTHUB_PROCESS_ITEM_RESULT

```C
enum IOTHUB_PROCESS_ITEM_RESULT {
  IOTHUB_PROCESS_OK,
  IOTHUB_PROCESS_ERROR,
  IOTHUB_PROCESS_NOT_CONNECTED,
  IOTHUB_PROCESS_CONTINUE
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUB_PROCESS_OK            | 
 IOTHUB_PROCESS_ERROR            | 
 IOTHUB_PROCESS_NOT_CONNECTED            | 
 IOTHUB_PROCESS_CONTINUE            | 

#### IOTHUBMESSAGE_DISPOSITION_RESULT

Enumeration returned by the callback which is invoked whenever the IoT Hub sends a message to the device. 

```C
enum IOTHUBMESSAGE_DISPOSITION_RESULT {
  IOTHUBMESSAGE_ACCEPTED,
  IOTHUBMESSAGE_REJECTED,
  IOTHUBMESSAGE_ABANDONED
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUBMESSAGE_ACCEPTED            | 
 IOTHUBMESSAGE_REJECTED            | 
 IOTHUBMESSAGE_ABANDONED            | 

#### IOTHUB_CLIENT_IOTHUB_METHOD_STATUS

Enumeration returned by remotely executed functions. 

```C
enum IOTHUB_CLIENT_IOTHUB_METHOD_STATUS {
  IOTHUB_CLIENT_IOTHUB_METHOD_STATUS_SUCCESS,
  IOTHUB_CLIENT_IOTHUB_METHOD_STATUS_ERROR
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUB_CLIENT_IOTHUB_METHOD_STATUS_SUCCESS            | 
 IOTHUB_CLIENT_IOTHUB_METHOD_STATUS_ERROR            | 

#### IOTHUB_CLIENT_CONFIRMATION_RESULT

Enumeration passed in by the IoT Hub when the event confirmation callback is invoked to indicate status of the event processing in the hub. 

```C
enum IOTHUB_CLIENT_CONFIRMATION_RESULT {
  IOTHUB_CLIENT_CONFIRMATION_OK,
  IOTHUB_CLIENT_CONFIRMATION_BECAUSE_DESTROY,
  IOTHUB_CLIENT_CONFIRMATION_MESSAGE_TIMEOUT,
  IOTHUB_CLIENT_CONFIRMATION_ERROR
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUB_CLIENT_CONFIRMATION_OK            | 
 IOTHUB_CLIENT_CONFIRMATION_BECAUSE_DESTROY            | 
 IOTHUB_CLIENT_CONFIRMATION_MESSAGE_TIMEOUT            | 
 IOTHUB_CLIENT_CONFIRMATION_ERROR            | 

#### IOTHUB_CLIENT_CONNECTION_STATUS

Enumeration passed in by the IoT Hub when the connection status callback is invoked to indicate status of the connection in the hub. 

```C
enum IOTHUB_CLIENT_CONNECTION_STATUS {
  IOTHUB_CLIENT_CONNECTION_AUTHENTICATED,
  IOTHUB_CLIENT_CONNECTION_UNAUTHENTICATED
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUB_CLIENT_CONNECTION_AUTHENTICATED            | 
 IOTHUB_CLIENT_CONNECTION_UNAUTHENTICATED            | 

#### IOTHUB_CLIENT_CONNECTION_STATUS_REASON

Enumeration passed in by the IoT Hub when the connection status callback is invoked to indicate status of the connection in the hub. 

```C
enum IOTHUB_CLIENT_CONNECTION_STATUS_REASON {
  IOTHUB_CLIENT_CONNECTION_EXPIRED_SAS_TOKEN,
  IOTHUB_CLIENT_CONNECTION_DEVICE_DISABLED,
  IOTHUB_CLIENT_CONNECTION_BAD_CREDENTIAL,
  IOTHUB_CLIENT_CONNECTION_RETRY_EXPIRED,
  IOTHUB_CLIENT_CONNECTION_NO_NETWORK,
  IOTHUB_CLIENT_CONNECTION_COMMUNICATION_ERROR,
  IOTHUB_CLIENT_CONNECTION_OK
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUB_CLIENT_CONNECTION_EXPIRED_SAS_TOKEN            | 
 IOTHUB_CLIENT_CONNECTION_DEVICE_DISABLED            | 
 IOTHUB_CLIENT_CONNECTION_BAD_CREDENTIAL            | 
 IOTHUB_CLIENT_CONNECTION_RETRY_EXPIRED            | 
 IOTHUB_CLIENT_CONNECTION_NO_NETWORK            | 
 IOTHUB_CLIENT_CONNECTION_COMMUNICATION_ERROR            | 
 IOTHUB_CLIENT_CONNECTION_OK            | 

#### TRANSPORT_TYPE

```C
enum TRANSPORT_TYPE {
  TRANSPORT_LL,
  TRANSPORT_THREADED
}

```
Constant                    | Description                                
----------------------------|----------------
 TRANSPORT_LL            | 
 TRANSPORT_THREADED            | 

#### DEVICE_TWIN_UPDATE_STATE

```C
enum DEVICE_TWIN_UPDATE_STATE {
  DEVICE_TWIN_UPDATE_COMPLETE,
  DEVICE_TWIN_UPDATE_PARTIAL
}

```
Constant                    | Description                                
----------------------------|----------------
 DEVICE_TWIN_UPDATE_COMPLETE            | 
 DEVICE_TWIN_UPDATE_PARTIAL            | 

#### IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_RESULT

```C
enum IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_RESULT {
  IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_OK,
  IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_ABORT
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_OK            | 
 IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_ABORT            | 

