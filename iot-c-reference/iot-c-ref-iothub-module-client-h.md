# Header file iothub_module_client.h 

Extends the IoTHubClient_LL module with additional features.

## Includes

\#include <stddef.h>  
\#include <stdint.h>  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include ["iothub_transport_ll.h"](iot-c-ref-iothub-transport-ll-h.md)  
\#include ["iothub_client_core_ll.h"](iot-c-ref-iothub-client-core-ll-h.md)  
\#include ["iothub_client_core.h"](iot-c-ref-iothub-client-core-h.md)  
\#include ["iothub_module_client_ll.h"](iot-c-ref-iothub-module-client-ll-h.md)  

## Detailed Description

IoTHubClient is a module that extends the IoTHubClient_LL module with 2 features:

* scheduling the work for the IoTHubClient from a thread, so that the user does not need to create their own thread

* thread-safe APIs

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IoTHubModuleClient_CreateFromConnectionString](./iot-c-ref-iothub-module-client-h/iothubmoduleclient-createfromconnectionstring.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using the specified connection string parameter.
[IoTHubModuleClient_Destroy](./iot-c-ref-iothub-module-client-h/iothubmoduleclient-destroy.md)            | Disposes of resources allocated by the IoT Hub client. This is a blocking call.
[IoTHubModuleClient_SendEventAsync](./iot-c-ref-iothub-module-client-h/iothubmoduleclient-sendeventasync.md)            | Asynchronous call to send the message specified by `eventMessageHandle`.
[IoTHubModuleClient_GetSendStatus](./iot-c-ref-iothub-module-client-h/iothubmoduleclient-getsendstatus.md)            | This function returns the current sending status for IoTHubClient.
[IoTHubModuleClient_SetMessageCallback](./iot-c-ref-iothub-module-client-h/iothubmoduleclient-setmessagecallback.md)            | Sets up the message callback to be invoked when IoT Hub issues a message to the device. This is a blocking call.
[IoTHubModuleClient_SetConnectionStatusCallback](./iot-c-ref-iothub-module-client-h/iothubmoduleclient-setconnectionstatuscallback.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubModuleClient_SetRetryPolicy](./iot-c-ref-iothub-module-client-h/iothubmoduleclient-setretrypolicy.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubModuleClient_GetRetryPolicy](./iot-c-ref-iothub-module-client-h/iothubmoduleclient-getretrypolicy.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubModuleClient_GetLastMessageReceiveTime](./iot-c-ref-iothub-module-client-h/iothubmoduleclient-getlastmessagereceivetime.md)            | This function returns in the out parameter `lastMessageReceiveTime` what was the value of the `time` function when the last message was received at the client.
[IoTHubModuleClient_SetOption](./iot-c-ref-iothub-module-client-h/iothubmoduleclient-setoption.md)            | This API sets a runtime option identified by parameter `optionName` to a value pointed to by `value`. `optionName` and the data type `value` is pointing to are specific for every option.
[IoTHubModuleClient_SetModuleTwinCallback](./iot-c-ref-iothub-module-client-h/iothubmoduleclient-setmoduletwincallback.md)            | This API specifies a call back to be used when the module receives a state update.
[IoTHubModuleClient_SendReportedState](./iot-c-ref-iothub-module-client-h/iothubmoduleclient-sendreportedstate.md)            | This API sends a report of the module's properties and their current values.
[IoTHubModuleClient_SetModuleMethodCallback](./iot-c-ref-iothub-module-client-h/iothubmoduleclient-setmodulemethodcallback.md)            | This API sets callback for async cloud to module method call.
[IoTHubModuleClient_SendEventToOutputAsync](./iot-c-ref-iothub-module-client-h/iothubmoduleclient-sendeventtooutputasync.md)            | Asynchronous call to send the message specified by `eventMessageHandle`.
[IoTHubModuleClient_SetInputMessageCallback](./iot-c-ref-iothub-module-client-h/iothubmoduleclient-setinputmessagecallback.md)            | This API sets callback for method call that is directed to specified 'inputName' queue (e.g. messages from IoTHubClient_SendEventToOutputAsync)

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IOTHUB_MODULE_CLIENT_INSTANCE_TYPE            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
IOTHUB_MODULE_CLIENT_HANDLE            | 

## Function documentation

#### IoTHubModuleClient_CreateFromConnectionString 
[IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) [IoTHubModuleClient_CreateFromConnectionString](#iothub__module__client_8h_1a56060237dbed8445a3e0ecc27654fa71)(const char * connectionString,[IOTHUB_CLIENT_TRANSPORT_PROVIDER](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)

#### IoTHubModuleClient_Destroy 
void [IoTHubModuleClient_Destroy](#iothub__module__client_8h_1af70545d139f41f0bc8acb51725c2d0de)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle)

#### IoTHubModuleClient_SendEventAsync 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_SendEventAsync](#iothub__module__client_8h_1a512d1335ba02912fed91a8ea00f0bd67)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,[IOTHUB_MESSAGE_HANDLE](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) eventMessageHandle,[IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK](#iothub__client__core__common_8h_1a41b17fcb2cb70587e3576226561648a0) eventConfirmationCallback,void * userContextCallback)

#### IoTHubModuleClient_GetSendStatus 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_GetSendStatus](#iothub__module__client_8h_1ae000ce091b36687df46e2a2658fa76c6)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,[IOTHUB_CLIENT_STATUS](#iothub__client__core__common_8h_1af80b6370369f3c1bb53399deccb4491c) * IoTHubClientStatus)

#### IoTHubModuleClient_SetMessageCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_SetMessageCallback](#iothub__module__client_8h_1a74fa92ba8f75ae3022b01fe5ca9f7fb0)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,[IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC](#iothub__client__core__common_8h_1adf7097e8fc9e34f26dd9347d4eaa5f8d) messageCallback,void * userContextCallback)

#### IoTHubModuleClient_SetConnectionStatusCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_SetConnectionStatusCallback](#iothub__module__client_8h_1a220d2191eed8a4854fb286b04b300c7e)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,[IOTHUB_CLIENT_CONNECTION_STATUS_CALLBACK](#iothub__client__core__common_8h_1ad0d7e0712e620b1d55e72652f4f4f560) connectionStatusCallback,void * userContextCallback)

#### IoTHubModuleClient_SetRetryPolicy 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_SetRetryPolicy](#iothub__module__client_8h_1a1604ce5a1caaa711d2a9b736046c3e50)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,[IOTHUB_CLIENT_RETRY_POLICY](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) retryPolicy,size_t retryTimeoutLimitInSeconds)

#### IoTHubModuleClient_GetRetryPolicy 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_GetRetryPolicy](#iothub__module__client_8h_1a96f0c8e7d91868a8919c0374918608c6)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,[IOTHUB_CLIENT_RETRY_POLICY](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) * retryPolicy,size_t * retryTimeoutLimitInSeconds)

#### IoTHubModuleClient_GetLastMessageReceiveTime 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_GetLastMessageReceiveTime](#iothub__module__client_8h_1a8547bb5912b9c29906527dcce9cd890c)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,time_t * lastMessageReceiveTime)

#### IoTHubModuleClient_SetOption 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_SetOption](#iothub__module__client_8h_1a8778c5207e84af1048d92ed4af6105c2)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,const char * optionName,const void * value)

#### IoTHubModuleClient_SetModuleTwinCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_SetModuleTwinCallback](#iothub__module__client_8h_1abc3d460b7d976dabc757d9dda0f96463)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,[IOTHUB_CLIENT_DEVICE_TWIN_CALLBACK](#iothub__client__core__common_8h_1a3020471f05025405840d9c43466122dc) moduleTwinCallback,void * userContextCallback)

#### IoTHubModuleClient_SendReportedState 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_SendReportedState](#iothub__module__client_8h_1a7bda16f4d71137f66482ac48f08299b7)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,const unsigned char * reportedState,size_t size,[IOTHUB_CLIENT_REPORTED_STATE_CALLBACK](#iothub__client__core__common_8h_1a9ae117da9222a5138e31a8953ce18bbc) reportedStateCallback,void * userContextCallback)

#### IoTHubModuleClient_SetModuleMethodCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_SetModuleMethodCallback](#iothub__module__client_8h_1a4aeb01ee89b410395815b025fc5df966)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) IoTHubClientHandle,[IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC](#iothub__client__core__common_8h_1aa758c6c04994938fae9257289760d01a) methodCallback,void * userContextCallback)

#### IoTHubModuleClient_SendEventToOutputAsync 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_SendEventToOutputAsync](#iothub__module__client_8h_1afc2a9b5f06dba7a48f189efe606ec8bb)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,[IOTHUB_MESSAGE_HANDLE](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) eventMessageHandle,const char * outputName,[IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK](#iothub__client__core__common_8h_1a41b17fcb2cb70587e3576226561648a0) eventConfirmationCallback,void * userContextCallback)

#### IoTHubModuleClient_SetInputMessageCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubModuleClient_SetInputMessageCallback](#iothub__module__client_8h_1a59375cb047c4b696e5eb8bfb9075fd5b)([IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) iotHubModuleClientHandle,const char * inputName,[IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC](#iothub__client__core__common_8h_1adf7097e8fc9e34f26dd9347d4eaa5f8d) eventHandlerCallback,void * userContextCallback)

