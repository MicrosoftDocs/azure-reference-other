# iothub_message.h 

The `IoTHub_Message` component encapsulates one message that can be transferred by an IoT hub client.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include "[azure_c_shared_utility/map.h](iot-c-ref-map-h.md)"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include <stddef.h>  

## Detailed Description

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IOTHUB_MESSAGE_RESULTStrings](./iot-c-ref-iothub-message-h/iothub-message-resultstrings.md)            | 
[IOTHUB_MESSAGE_RESULT_FromString](./iot-c-ref-iothub-message-h/iothub-message-result-fromstring.md)            | 
[IOTHUBMESSAGE_CONTENT_TYPEStrings](./iot-c-ref-iothub-message-h/iothubmessage-content-typestrings.md)            | 
[IOTHUBMESSAGE_CONTENT_TYPE_FromString](./iot-c-ref-iothub-message-h/iothubmessage-content-type-fromstring.md)            | 
[IoTHubMessage_CreateFromByteArray](./iot-c-ref-iothub-message-h/iothubmessage-createfrombytearray.md)            | Creates a new IoT hub message from a byte array. The type of the message will be set to `IOTHUBMESSAGE_BYTEARRAY`.
[IoTHubMessage_CreateFromString](./iot-c-ref-iothub-message-h/iothubmessage-createfromstring.md)            | Creates a new IoT hub message from a null terminated string. The type of the message will be set to `IOTHUBMESSAGE_STRING`.
[IoTHubMessage_Clone](./iot-c-ref-iothub-message-h/iothubmessage-clone.md)            | Creates a new IoT hub message with the content identical to that of the `iotHubMessageHandle` parameter.
[IoTHubMessage_GetByteArray](./iot-c-ref-iothub-message-h/iothubmessage-getbytearray.md)            | Fetches a pointer and size for the data associated with the IoT hub message handle. If the content type of the message is not `IOTHUBMESSAGE_BYTEARRAY` then the function returns `IOTHUB_MESSAGE_INVALID_ARG`.
[IoTHubMessage_GetString](./iot-c-ref-iothub-message-h/iothubmessage-getstring.md)            | Returns the null terminated string stored in the message. If the content type of the message is not `IOTHUBMESSAGE_STRING` then the function returns `NULL`.
[IoTHubMessage_GetContentType](./iot-c-ref-iothub-message-h/iothubmessage-getcontenttype.md)            | Returns the content type of the message given by parameter `iotHubMessageHandle`.
[IoTHubMessage_SetContentTypeSystemProperty](./iot-c-ref-iothub-message-h/iothubmessage-setcontenttypesystemproperty.md)            | Sets the content-type of the message payload, as per supported values on RFC 2046.
[IoTHubMessage_GetContentTypeSystemProperty](./iot-c-ref-iothub-message-h/iothubmessage-getcontenttypesystemproperty.md)            | Returns the content-type of the message payload, if defined.
[IoTHubMessage_SetContentEncodingSystemProperty](./iot-c-ref-iothub-message-h/iothubmessage-setcontentencodingsystemproperty.md)            | Sets the content-encoding of the message payload, as per supported values on RFC 2616.
[IoTHubMessage_GetContentEncodingSystemProperty](./iot-c-ref-iothub-message-h/iothubmessage-getcontentencodingsystemproperty.md)            | Returns the content-encoding of the message payload, if defined.
[IoTHubMessage_Properties](./iot-c-ref-iothub-message-h/iothubmessage-properties.md)            | Gets a handle to the message's properties map. Note that when sending messages via the HTTP transport, the key names in the map must not contain spaces.
[IoTHubMessage_SetProperty](./iot-c-ref-iothub-message-h/iothubmessage-setproperty.md)            | Sets a property on a Iothub Message.
[IoTHubMessage_GetProperty](./iot-c-ref-iothub-message-h/iothubmessage-getproperty.md)            | Gets a IotHub Message's properties item.
[IoTHubMessage_GetMessageId](./iot-c-ref-iothub-message-h/iothubmessage-getmessageid.md)            | Gets the MessageId from the IOTHUB_MESSAGE_HANDLE.
[IoTHubMessage_SetMessageId](./iot-c-ref-iothub-message-h/iothubmessage-setmessageid.md)            | Sets the MessageId for the IOTHUB_MESSAGE_HANDLE.
[IoTHubMessage_GetCorrelationId](./iot-c-ref-iothub-message-h/iothubmessage-getcorrelationid.md)            | Gets the CorrelationId from the IOTHUB_MESSAGE_HANDLE.
[IoTHubMessage_SetCorrelationId](./iot-c-ref-iothub-message-h/iothubmessage-setcorrelationid.md)            | Sets the CorrelationId for the IOTHUB_MESSAGE_HANDLE.
[IoTHubMessage_GetDiagnosticPropertyData](./iot-c-ref-iothub-message-h/iothubmessage-getdiagnosticpropertydata.md)            | Gets the DiagnosticData from the IOTHUB_MESSAGE_HANDLE. CAUTION: SDK user should not call it directly, it is for internal use only.
[IoTHubMessage_SetDiagnosticPropertyData](./iot-c-ref-iothub-message-h/iothubmessage-setdiagnosticpropertydata.md)            | Sets the DiagnosticData for the IOTHUB_MESSAGE_HANDLE. CAUTION: SDK user should not call it directly, it is for internal use only.
[IoTHubMessage_GetOutputName](./iot-c-ref-iothub-message-h/iothubmessage-getoutputname.md)            | Gets the output name from the IOTHUB_MESSAGE_HANDLE.
[IoTHubMessage_SetOutputName](./iot-c-ref-iothub-message-h/iothubmessage-setoutputname.md)            | Sets output for named queues. CAUTION: SDK user should not call it directly, it is for internal use only.
[IoTHubMessage_GetInputName](./iot-c-ref-iothub-message-h/iothubmessage-getinputname.md)            | Gets the input name from the IOTHUB_MESSAGE_HANDLE.
[IoTHubMessage_SetInputName](./iot-c-ref-iothub-message-h/iothubmessage-setinputname.md)            | Sets input for named queues. CAUTION: SDK user should not call it directly, it is for internal use only.
[IoTHubMessage_GetConnectionModuleId](./iot-c-ref-iothub-message-h/iothubmessage-getconnectionmoduleid.md)            | Gets the module name from the IOTHUB_MESSAGE_HANDLE.
[IoTHubMessage_SetConnectionModuleId](./iot-c-ref-iothub-message-h/iothubmessage-setconnectionmoduleid.md)            | Sets connection module ID. CAUTION: SDK user should not call it directly, it is for internal use only.
[IoTHubMessage_GetConnectionDeviceId](./iot-c-ref-iothub-message-h/iothubmessage-getconnectiondeviceid.md)            | Gets the connection device ID from the IOTHUB_MESSAGE_HANDLE.
[IoTHubMessage_SetConnectionDeviceId](./iot-c-ref-iothub-message-h/iothubmessage-setconnectiondeviceid.md)            | Sets connection device Id. CAUTION: SDK user should not call it directly, it is for internal use only.
[IoTHubMessage_Destroy](./iot-c-ref-iothub-message-h/iothubmessage-destroy.md)            | Frees all resources associated with the given message handle.

## Structures

#### IOTHUB_MESSAGE_DIAGNOSTIC_PROPERTY_DATA

```C
struct IOTHUB_MESSAGE_DIAGNOSTIC_PROPERTY_DATA{
  char *  diagnosticId,
  char *  diagnosticCreationTimeUtc
};
```

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IOTHUB_MESSAGE_RESULT_VALUES            | 
IOTHUBMESSAGE_CONTENT_TYPE_VALUES            | 

## Typedefs

#### IOTHUB_MESSAGE_HANDLE

```C
typedef struct IOTHUB_MESSAGE_HANDLE_DATA_TAG * IOTHUB_MESSAGE_HANDLE;

```

