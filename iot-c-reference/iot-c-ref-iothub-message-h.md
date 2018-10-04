# Header file iothub_message.h 

The `IoTHub_Message` component encapsulates one message that can be transferred by an IoT hub client.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_c_shared_utility/map.h"](iot-c-ref-map-h.md)  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
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

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IOTHUB_MESSAGE_RESULT_VALUES            | 
IOTHUBMESSAGE_CONTENT_TYPE_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
IOTHUB_MESSAGE_HANDLE            | 

## Function documentation

#### IOTHUB_MESSAGE_RESULTStrings 
const char * `[`IOTHUB_MESSAGE_RESULTStrings`](#iothub__message_8h_1a9256e187c0ef121b7a17f2e77ae3f0a2)(`[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) value)`

#### IOTHUB_MESSAGE_RESULT_FromString 
int `[`IOTHUB_MESSAGE_RESULT_FromString`](#iothub__message_8h_1a10109f572fcad90e3f728b6ab9783636)(const char * enumAsString,`[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) * destination)`

#### IOTHUBMESSAGE_CONTENT_TYPEStrings 
const char * `[`IOTHUBMESSAGE_CONTENT_TYPEStrings`](#iothub__message_8h_1ac997fd4ddf506d8b324b6d01d039ff94)(`[`IOTHUBMESSAGE_CONTENT_TYPE`](#iothub__message_8h_1aea6d5176bef9e4c53f015b35f5f32d16) value)`

#### IOTHUBMESSAGE_CONTENT_TYPE_FromString 
int `[`IOTHUBMESSAGE_CONTENT_TYPE_FromString`](#iothub__message_8h_1a48d0e3bf35565003852b7b28a0ef4678)(const char * enumAsString,`[`IOTHUBMESSAGE_CONTENT_TYPE`](#iothub__message_8h_1aea6d5176bef9e4c53f015b35f5f32d16) * destination)`

#### IoTHubMessage_CreateFromByteArray 
[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) `[`IoTHubMessage_CreateFromByteArray`](#iothub__message_8h_1acaa3b835c12fb0254938af052f0fcb6f)(const unsigned char * byteArray,size_t size)`

#### IoTHubMessage_CreateFromString 
[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) `[`IoTHubMessage_CreateFromString`](#iothub__message_8h_1a8b44199b87bd177d1a85671faef657db)(const char * source)`

#### IoTHubMessage_Clone 
[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) `[`IoTHubMessage_Clone`](#iothub__message_8h_1ab5c68ff6fbb9dbe613c8b981f4c202b4)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

#### IoTHubMessage_GetByteArray 
[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) `[`IoTHubMessage_GetByteArray`](#iothub__message_8h_1afac0461ed8c3d522bbf2a4cfa9f3f957)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const unsigned char ** buffer,size_t * size)`

#### IoTHubMessage_GetString 
const char * `[`IoTHubMessage_GetString`](#iothub__message_8h_1aaf63b9aecdde6f8c90d9fbd0755d0c41)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

#### IoTHubMessage_GetContentType 
[`IOTHUBMESSAGE_CONTENT_TYPE`](#iothub__message_8h_1aea6d5176bef9e4c53f015b35f5f32d16) `[`IoTHubMessage_GetContentType`](#iothub__message_8h_1ae7fd8e5a5844a4346933a86feb577d3c)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

#### IoTHubMessage_SetContentTypeSystemProperty 
[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) `[`IoTHubMessage_SetContentTypeSystemProperty`](#iothub__message_8h_1af5961a16ad97a128434cbdde78a91b4c)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * contentType)`

#### IoTHubMessage_GetContentTypeSystemProperty 
const char * `[`IoTHubMessage_GetContentTypeSystemProperty`](#iothub__message_8h_1ab01841e548f7119ab833be50695de241)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

#### IoTHubMessage_SetContentEncodingSystemProperty 
[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) `[`IoTHubMessage_SetContentEncodingSystemProperty`](#iothub__message_8h_1abd1c044606f8c70df4f1af9b19a7a85f)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * contentEncoding)`

#### IoTHubMessage_GetContentEncodingSystemProperty 
const char * `[`IoTHubMessage_GetContentEncodingSystemProperty`](#iothub__message_8h_1ab3db6de666d01e3d5730e1d2db592832)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

#### IoTHubMessage_Properties 
[`MAP_HANDLE`](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) `[`IoTHubMessage_Properties`](#iothub__message_8h_1a2ab46db5ad9db0b497b5171e21b64ea2)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

#### IoTHubMessage_SetProperty 
[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) `[`IoTHubMessage_SetProperty`](#iothub__message_8h_1accde5b88b49e4fd3ebfdf54c97390d88)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * key,const char * value)`

#### IoTHubMessage_GetProperty 
const char * `[`IoTHubMessage_GetProperty`](#iothub__message_8h_1ab3deb99bb741380be15ae8dcdcee6316)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * key)`

#### IoTHubMessage_GetMessageId 
const char * `[`IoTHubMessage_GetMessageId`](#iothub__message_8h_1ada4fa36e8ab3af2759a6e5703d55dc29)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

#### IoTHubMessage_SetMessageId 
[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) `[`IoTHubMessage_SetMessageId`](#iothub__message_8h_1a3d5f3d8a6da59b259f170de613c61cc0)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * messageId)`

#### IoTHubMessage_GetCorrelationId 
const char * `[`IoTHubMessage_GetCorrelationId`](#iothub__message_8h_1aac9f6f33fc89f91ffa7853692a1555b6)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

#### IoTHubMessage_SetCorrelationId 
[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) `[`IoTHubMessage_SetCorrelationId`](#iothub__message_8h_1afcc4a3e4e8ac287b0a9a3850c5a72248)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * correlationId)`

#### IoTHubMessage_GetDiagnosticPropertyData 
const [`IOTHUB_MESSAGE_DIAGNOSTIC_PROPERTY_DATA`](#struct_i_o_t_h_u_b___m_e_s_s_a_g_e___d_i_a_g_n_o_s_t_i_c___p_r_o_p_e_r_t_y___d_a_t_a) * `[`IoTHubMessage_GetDiagnosticPropertyData`](#iothub__message_8h_1af9a6a0e67384e6194a5d3fde2dd149e9)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

#### IoTHubMessage_SetDiagnosticPropertyData 
[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) `[`IoTHubMessage_SetDiagnosticPropertyData`](#iothub__message_8h_1aa5244a4e3d077c11023fc84cabd09203)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const `[`IOTHUB_MESSAGE_DIAGNOSTIC_PROPERTY_DATA`](#struct_i_o_t_h_u_b___m_e_s_s_a_g_e___d_i_a_g_n_o_s_t_i_c___p_r_o_p_e_r_t_y___d_a_t_a) * diagnosticData)`

#### IoTHubMessage_GetOutputName 
const char * `[`IoTHubMessage_GetOutputName`](#iothub__message_8h_1aaa95a80c4f77a43c6c0e596b6ceb1997)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

#### IoTHubMessage_SetOutputName 
[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) `[`IoTHubMessage_SetOutputName`](#iothub__message_8h_1aaa130a5879907e939c7724d0ed544176)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * outputName)`

#### IoTHubMessage_GetInputName 
const char * `[`IoTHubMessage_GetInputName`](#iothub__message_8h_1a55cb0a7f19b8c39652ba4090a34671a9)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

#### IoTHubMessage_SetInputName 
[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) `[`IoTHubMessage_SetInputName`](#iothub__message_8h_1aa8dd031bb670f90a791c018bbd6474cd)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * inputName)`

#### IoTHubMessage_GetConnectionModuleId 
const char * `[`IoTHubMessage_GetConnectionModuleId`](#iothub__message_8h_1ad4dc37f28c9b4f82e6ab63bcca83e19b)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

#### IoTHubMessage_SetConnectionModuleId 
[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) `[`IoTHubMessage_SetConnectionModuleId`](#iothub__message_8h_1ac2161d4ff09fc91b0869533359d5ecd5)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * connectionModuleId)`

#### IoTHubMessage_GetConnectionDeviceId 
const char * `[`IoTHubMessage_GetConnectionDeviceId`](#iothub__message_8h_1a1e04618fe0efb5981c8bc744bd360d76)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

#### IoTHubMessage_SetConnectionDeviceId 
[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) `[`IoTHubMessage_SetConnectionDeviceId`](#iothub__message_8h_1aa0fb6d672633c802fdf976ac43015589)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const char * connectionDeviceId)`

#### IoTHubMessage_Destroy 
void `[`IoTHubMessage_Destroy`](#iothub__message_8h_1a8303de9790f32c3b0aebac6cfb0e80bf)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

