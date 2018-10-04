# Header file iothub_module_client_ll.h 

APIs that allow a user (usually a module) to communicate with an Azure IoTHub.

## Includes

\#include <time.h>  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include ["iothub_transport_ll.h"](iot-c-ref-iothub-transport-ll-h.md)  
\#include ["iothub_client_core_common.h"](iot-c-ref-iothub-client-core-common-h.md)  
\#include <stddef.h>  
\#include <stdint.h>  

## Detailed Description

IoTHubModuleClient_LL is a module that allows a user (usually a module) to communicate with an Azure IoTHub. It can send events and receive messages. At any given moment in time there can only be at most 1 message callback function.

This API surface contains a set of APIs that allows the user to interact with the lower layer portion of the IoTHubClient. These APIs contain `_LL_` in their name, but retain the same functionality like the `IoTHubModuleClient_`... APIs, with one difference. If the `_LL_` APIs are used then the user is responsible for scheduling when the actual work done by the IoTHubClient happens (when the data is sent/received on/from the wire). This is useful for constrained devices where spinning a separate thread is often not desired.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IoTHubModuleClient_LL_CreateFromConnectionString](./iot-c-ref-iothub-module-client-ll-h/iothubmoduleclient-ll-createfromconnectionstring.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using the specified connection string parameter.
[IoTHubModuleClient_LL_Destroy](./iot-c-ref-iothub-module-client-ll-h/iothubmoduleclient-ll-destroy.md)            | Disposes of resources allocated by the IoT Hub client. This is a blocking call.
[IoTHubModuleClient_LL_SendEventAsync](./iot-c-ref-iothub-module-client-ll-h/iothubmoduleclient-ll-sendeventasync.md)            | Asynchronous call to send the message specified by `eventMessageHandle`.
[IoTHubModuleClient_LL_GetSendStatus](./iot-c-ref-iothub-module-client-ll-h/iothubmoduleclient-ll-getsendstatus.md)            | This function returns the current sending status for IoTHubClient.
[IoTHubModuleClient_LL_SetMessageCallback](./iot-c-ref-iothub-module-client-ll-h/iothubmoduleclient-ll-setmessagecallback.md)            | Sets up the message callback to be invoked when Edge issues a message to the module. This is a blocking call.
[IoTHubModuleClient_LL_SetConnectionStatusCallback](./iot-c-ref-iothub-module-client-ll-h/iothubmoduleclient-ll-setconnectionstatuscallback.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubModuleClient_LL_SetRetryPolicy](./iot-c-ref-iothub-module-client-ll-h/iothubmoduleclient-ll-setretrypolicy.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubModuleClient_LL_GetRetryPolicy](./iot-c-ref-iothub-module-client-ll-h/iothubmoduleclient-ll-getretrypolicy.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubModuleClient_LL_GetLastMessageReceiveTime](./iot-c-ref-iothub-module-client-ll-h/iothubmoduleclient-ll-getlastmessagereceivetime.md)            | This function returns in the out parameter `lastMessageReceiveTime` what was the value of the `time` function when the last message was received at the client.
[IoTHubModuleClient_LL_DoWork](./iot-c-ref-iothub-module-client-ll-h/iothubmoduleclient-ll-dowork.md)            | This function is meant to be called by the user when work (sending/receiving) can be done by the IoTHubClient.
[IoTHubModuleClient_LL_SetOption](./iot-c-ref-iothub-module-client-ll-h/iothubmoduleclient-ll-setoption.md)            | This API sets a runtime option identified by parameter `optionName` to a value pointed to by `value`. `optionName` and the data type `value` is pointing to are specific for every option.
[IoTHubModuleClient_LL_SetModuleTwinCallback](./iot-c-ref-iothub-module-client-ll-h/iothubmoduleclient-ll-setmoduletwincallback.md)            | This API specifies a call back to be used when the module receives a desired state update.
[IoTHubModuleClient_LL_SendReportedState](./iot-c-ref-iothub-module-client-ll-h/iothubmoduleclient-ll-sendreportedstate.md)            | This API sneds a report of the module's properties and their current values.
[IoTHubModuleClient_LL_SetModuleMethodCallback](./iot-c-ref-iothub-module-client-ll-h/iothubmoduleclient-ll-setmodulemethodcallback.md)            | This API sets callback for async cloud to module method call.
[IoTHubModuleClient_LL_SendEventToOutputAsync](./iot-c-ref-iothub-module-client-ll-h/iothubmoduleclient-ll-sendeventtooutputasync.md)            | Asynchronous call to send the message specified by `eventMessageHandle`.
[IoTHubModuleClient_LL_SetInputMessageCallback](./iot-c-ref-iothub-module-client-ll-h/iothubmoduleclient-ll-setinputmessagecallback.md)            | This API sets callback for method call that is directed to specified 'inputName' queue (e.g. messages from IoTHubClient_SendEventToOutputAsync)

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
IOTHUB_MODULE_CLIENT_LL_HANDLE            | 

## Function documentation

#### IoTHubModuleClient_LL_CreateFromConnectionString 
[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) `[`IoTHubModuleClient_LL_CreateFromConnectionString`](#iothub__module__client__ll_8h_1ab99ab4387fd82182d98e7231615eaf8f)(const char * connectionString,`[`IOTHUB_CLIENT_TRANSPORT_PROVIDER`](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)`

#### IoTHubModuleClient_LL_Destroy 
void `[`IoTHubModuleClient_LL_Destroy`](#iothub__module__client__ll_8h_1aad2dd6c3c24f89a9cfa861754a845138)(`[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle)`

#### IoTHubModuleClient_LL_SendEventAsync 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_LL_SendEventAsync`](#iothub__module__client__ll_8h_1a51e76624cbf23f5538efc4bf705ba178)(`[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) eventMessageHandle,`[`IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK`](#iothub__client__core__common_8h_1a41b17fcb2cb70587e3576226561648a0) eventConfirmationCallback,void * userContextCallback)`

#### IoTHubModuleClient_LL_GetSendStatus 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_LL_GetSendStatus`](#iothub__module__client__ll_8h_1aea417d74c48aaa56c37db8478f6539db)(`[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,`[`IOTHUB_CLIENT_STATUS`](#iothub__client__core__common_8h_1af80b6370369f3c1bb53399deccb4491c) * iotHubClientStatus)`

#### IoTHubModuleClient_LL_SetMessageCallback 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_LL_SetMessageCallback`](#iothub__module__client__ll_8h_1a401b3c56c9302d2a9a8ebde282305b9f)(`[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,`[`IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC`](#iothub__client__core__common_8h_1adf7097e8fc9e34f26dd9347d4eaa5f8d) messageCallback,void * userContextCallback)`

#### IoTHubModuleClient_LL_SetConnectionStatusCallback 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_LL_SetConnectionStatusCallback`](#iothub__module__client__ll_8h_1a36867f994c46aa2a38df078c26ebe159)(`[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,`[`IOTHUB_CLIENT_CONNECTION_STATUS_CALLBACK`](#iothub__client__core__common_8h_1ad0d7e0712e620b1d55e72652f4f4f560) connectionStatusCallback,void * userContextCallback)`

#### IoTHubModuleClient_LL_SetRetryPolicy 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_LL_SetRetryPolicy`](#iothub__module__client__ll_8h_1ac59a75424dde5f3c9340bc8b8fbf61bb)(`[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,`[`IOTHUB_CLIENT_RETRY_POLICY`](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) retryPolicy,size_t retryTimeoutLimitInSeconds)`

#### IoTHubModuleClient_LL_GetRetryPolicy 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_LL_GetRetryPolicy`](#iothub__module__client__ll_8h_1a99e5348c08f19c5f65ab9052ce5e592d)(`[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,`[`IOTHUB_CLIENT_RETRY_POLICY`](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) * retryPolicy,size_t * retryTimeoutLimitInSeconds)`

#### IoTHubModuleClient_LL_GetLastMessageReceiveTime 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_LL_GetLastMessageReceiveTime`](#iothub__module__client__ll_8h_1a179a3203b8865755dc8ac9fd9128b41e)(`[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,time_t * lastMessageReceiveTime)`

#### IoTHubModuleClient_LL_DoWork 
void `[`IoTHubModuleClient_LL_DoWork`](#iothub__module__client__ll_8h_1a11c622cd616f20a3f4cdc10d48c1eac1)(`[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle)`

#### IoTHubModuleClient_LL_SetOption 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_LL_SetOption`](#iothub__module__client__ll_8h_1adb6c8f4bfd2c26200580f04dabcfd132)(`[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,const char * optionName,const void * value)`

#### IoTHubModuleClient_LL_SetModuleTwinCallback 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_LL_SetModuleTwinCallback`](#iothub__module__client__ll_8h_1a7f2a499a88bb224f273e5c20ce881b20)(`[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,`[`IOTHUB_CLIENT_DEVICE_TWIN_CALLBACK`](#iothub__client__core__common_8h_1a3020471f05025405840d9c43466122dc) moduleTwinCallback,void * userContextCallback)`

#### IoTHubModuleClient_LL_SendReportedState 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_LL_SendReportedState`](#iothub__module__client__ll_8h_1a44519374217fca11ad0faa4f8e1cb08d)(`[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,const unsigned char * reportedState,size_t size,`[`IOTHUB_CLIENT_REPORTED_STATE_CALLBACK`](#iothub__client__core__common_8h_1a9ae117da9222a5138e31a8953ce18bbc) reportedStateCallback,void * userContextCallback)`

#### IoTHubModuleClient_LL_SetModuleMethodCallback 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_LL_SetModuleMethodCallback`](#iothub__module__client__ll_8h_1a9eb4748db53e83c2d28608599ee6f267)(`[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,`[`IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC`](#iothub__client__core__common_8h_1aa758c6c04994938fae9257289760d01a) moduleMethodCallback,void * userContextCallback)`

#### IoTHubModuleClient_LL_SendEventToOutputAsync 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_LL_SendEventToOutputAsync`](#iothub__module__client__ll_8h_1a86ff46caf2e048ec9e6e2a7b764c51fa)(`[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) eventMessageHandle,const char * outputName,`[`IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK`](#iothub__client__core__common_8h_1a41b17fcb2cb70587e3576226561648a0) eventConfirmationCallback,void * userContextCallback)`

#### IoTHubModuleClient_LL_SetInputMessageCallback 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubModuleClient_LL_SetInputMessageCallback`](#iothub__module__client__ll_8h_1a54f3398271f5be3f21c0ed41574b2f82)(`[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) iotHubModuleClientHandle,const char * inputName,`[`IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC`](#iothub__client__core__common_8h_1adf7097e8fc9e34f26dd9347d4eaa5f8d) eventHandlerCallback,void * userContextCallback)`

