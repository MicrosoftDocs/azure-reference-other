# Header file iothub_client.h 

Extends the IoTHubCLient_LL module with additional features.

## Includes

\#include <stddef.h>  
\#include <stdint.h>  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include ["iothub_transport_ll.h"](iot-c-ref-iothub-transport-ll-h.md)  
\#include ["iothub_client_core_ll.h"](iot-c-ref-iothub-client-core-ll-h.md)  
\#include ["iothub_client_core.h"](iot-c-ref-iothub-client-core-h.md)  
\#include ["iothub_client_ll.h"](iot-c-ref-iothub-client-ll-h.md)  

## Detailed Description

IoTHubClient is a module that extends the IoTHubCLient_LL module with 2 features:

* scheduling the work for the IoTHubCLient from a thread, so that the user does not need to create their own thread

* thread-safe APIs

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IoTHubClient_CreateFromConnectionString](./iot-c-ref-iothub-client-h/iothubclient-createfromconnectionstring.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using the specified connection string parameter.
[IoTHubClient_Create](./iot-c-ref-iothub-client-h/iothubclient-create.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using the specified parameters.
[IoTHubClient_CreateWithTransport](./iot-c-ref-iothub-client-h/iothubclient-createwithtransport.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using the specified parameters.
[IoTHubClient_CreateFromDeviceAuth](./iot-c-ref-iothub-client-h/iothubclient-createfromdeviceauth.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using the device auth module.
[IoTHubClient_Destroy](./iot-c-ref-iothub-client-h/iothubclient-destroy.md)            | Disposes of resources allocated by the IoT Hub client. This is a blocking call.
[IoTHubClient_SendEventAsync](./iot-c-ref-iothub-client-h/iothubclient-sendeventasync.md)            | Asynchronous call to send the message specified by `eventMessageHandle`.
[IoTHubClient_GetSendStatus](./iot-c-ref-iothub-client-h/iothubclient-getsendstatus.md)            | This function returns the current sending status for IoTHubClient.
[IoTHubClient_SetMessageCallback](./iot-c-ref-iothub-client-h/iothubclient-setmessagecallback.md)            | Sets up the message callback to be invoked when IoT Hub issues a message to the device. This is a blocking call.
[IoTHubClient_SetConnectionStatusCallback](./iot-c-ref-iothub-client-h/iothubclient-setconnectionstatuscallback.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubClient_SetRetryPolicy](./iot-c-ref-iothub-client-h/iothubclient-setretrypolicy.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubClient_GetRetryPolicy](./iot-c-ref-iothub-client-h/iothubclient-getretrypolicy.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubClient_GetLastMessageReceiveTime](./iot-c-ref-iothub-client-h/iothubclient-getlastmessagereceivetime.md)            | This function returns in the out parameter `lastMessageReceiveTime` what was the value of the `time` function when the last message was received at the client.
[IoTHubClient_SetOption](./iot-c-ref-iothub-client-h/iothubclient-setoption.md)            | This API sets a runtime option identified by parameter `optionName` to a value pointed to by `value`. `optionName` and the data type `value` is pointing to are specific for every option.
[IoTHubClient_SetDeviceTwinCallback](./iot-c-ref-iothub-client-h/iothubclient-setdevicetwincallback.md)            | This API specifies a call back to be used when the device receives a state update.
[IoTHubClient_SendReportedState](./iot-c-ref-iothub-client-h/iothubclient-sendreportedstate.md)            | This API sends a report of the device's properties and their current values.
[IoTHubClient_SetDeviceMethodCallback](./iot-c-ref-iothub-client-h/iothubclient-setdevicemethodcallback.md)            | This API sets callback for cloud to device method call.
[IoTHubClient_SetDeviceMethodCallback_Ex](./iot-c-ref-iothub-client-h/iothubclient-setdevicemethodcallback-ex.md)            | This API sets callback for async cloud to device method call.
[IoTHubClient_DeviceMethodResponse](./iot-c-ref-iothub-client-h/iothubclient-devicemethodresponse.md)            | This API responses to a asnyc method callback identified the methodId.
[IoTHubClient_UploadToBlobAsync](./iot-c-ref-iothub-client-h/iothubclient-uploadtoblobasync.md)            | IoTHubClient_UploadToBlobAsync uploads data from memory to a file in Azure Blob Storage.
[IoTHubClient_UploadMultipleBlocksToBlobAsync](./iot-c-ref-iothub-client-h/iothubclient-uploadmultipleblockstoblobasync.md)            | Uploads a file to a Blob storage in chunks, fed through the callback function provided by the user.
[IoTHubClient_UploadMultipleBlocksToBlobAsyncEx](./iot-c-ref-iothub-client-h/iothubclient-uploadmultipleblockstoblobasyncex.md)            | Uploads a file to a Blob storage in chunks, fed through the callback function provided by the user.

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IOTHUB_CLIENT_INSTANCE_TYPE            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
IOTHUB_CLIENT_HANDLE            | 

## Function documentation

#### IoTHubClient_CreateFromConnectionString 
[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) `[`IoTHubClient_CreateFromConnectionString`](#iothub__client_8h_1a190e08e1201046fda675517070d63e83)(const char * connectionString,`[`IOTHUB_CLIENT_TRANSPORT_PROVIDER`](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)`

#### IoTHubClient_Create 
[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) `[`IoTHubClient_Create`](#iothub__client_8h_1a7e4253f4df8cdef79cbe44d33c73547d)(const `[`IOTHUB_CLIENT_CONFIG`](#struct_i_o_t_h_u_b___c_l_i_e_n_t___c_o_n_f_i_g) * config)`

#### IoTHubClient_CreateWithTransport 
[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) `[`IoTHubClient_CreateWithTransport`](#iothub__client_8h_1a2eb95b5592c8c1c5e1fed5cef60ba0ff)(`[`TRANSPORT_HANDLE`](#iothub__transport__ll_8h_1a085a6035b065e4f48f3789e428235aa4) transportHandle,const `[`IOTHUB_CLIENT_CONFIG`](#struct_i_o_t_h_u_b___c_l_i_e_n_t___c_o_n_f_i_g) * config)`

#### IoTHubClient_CreateFromDeviceAuth 
[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) `[`IoTHubClient_CreateFromDeviceAuth`](#iothub__client_8h_1ac10dff7a369ef9c39babca7ce4a69476)(const char * iothub_uri,const char * device_id,`[`IOTHUB_CLIENT_TRANSPORT_PROVIDER`](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)`

#### IoTHubClient_Destroy 
void `[`IoTHubClient_Destroy`](#iothub__client_8h_1a47fce212d1c5026e02ccd670242e1d83)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle)`

#### IoTHubClient_SendEventAsync 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_SendEventAsync`](#iothub__client_8h_1a3e60e953d03a503c1ae30dd6af7f390f)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) eventMessageHandle,`[`IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK`](#iothub__client__core__common_8h_1a41b17fcb2cb70587e3576226561648a0) eventConfirmationCallback,void * userContextCallback)`

#### IoTHubClient_GetSendStatus 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_GetSendStatus`](#iothub__client_8h_1a692ed29a02e5842a60db1b3c0ce1b186)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,`[`IOTHUB_CLIENT_STATUS`](#iothub__client__core__common_8h_1af80b6370369f3c1bb53399deccb4491c) * iotHubClientStatus)`

#### IoTHubClient_SetMessageCallback 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_SetMessageCallback`](#iothub__client_8h_1a86d2a2ad2209f6e33bf59ee586abc042)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,`[`IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC`](#iothub__client__core__common_8h_1adf7097e8fc9e34f26dd9347d4eaa5f8d) messageCallback,void * userContextCallback)`

#### IoTHubClient_SetConnectionStatusCallback 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_SetConnectionStatusCallback`](#iothub__client_8h_1a6fb9f6dbb0fdf87d62ed457f2f285dac)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,`[`IOTHUB_CLIENT_CONNECTION_STATUS_CALLBACK`](#iothub__client__core__common_8h_1ad0d7e0712e620b1d55e72652f4f4f560) connectionStatusCallback,void * userContextCallback)`

#### IoTHubClient_SetRetryPolicy 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_SetRetryPolicy`](#iothub__client_8h_1acda949e1d5657a858a071ca8da90232a)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,`[`IOTHUB_CLIENT_RETRY_POLICY`](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) retryPolicy,size_t retryTimeoutLimitInSeconds)`

#### IoTHubClient_GetRetryPolicy 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_GetRetryPolicy`](#iothub__client_8h_1a4d7cab2213f5f82aac7d60fca5e519bc)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,`[`IOTHUB_CLIENT_RETRY_POLICY`](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) * retryPolicy,size_t * retryTimeoutLimitInSeconds)`

#### IoTHubClient_GetLastMessageReceiveTime 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_GetLastMessageReceiveTime`](#iothub__client_8h_1a4484e3db3c295c66d379b44fc53cfd79)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,time_t * lastMessageReceiveTime)`

#### IoTHubClient_SetOption 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_SetOption`](#iothub__client_8h_1a7a0ff66340551d6748b13e9ca74f3197)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,const char * optionName,const void * value)`

#### IoTHubClient_SetDeviceTwinCallback 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_SetDeviceTwinCallback`](#iothub__client_8h_1a447f057c69117c3c36c6b13de05e2001)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,`[`IOTHUB_CLIENT_DEVICE_TWIN_CALLBACK`](#iothub__client__core__common_8h_1a3020471f05025405840d9c43466122dc) deviceTwinCallback,void * userContextCallback)`

#### IoTHubClient_SendReportedState 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_SendReportedState`](#iothub__client_8h_1ac34cf252e6306068821ede9131606cc4)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,const unsigned char * reportedState,size_t size,`[`IOTHUB_CLIENT_REPORTED_STATE_CALLBACK`](#iothub__client__core__common_8h_1a9ae117da9222a5138e31a8953ce18bbc) reportedStateCallback,void * userContextCallback)`

#### IoTHubClient_SetDeviceMethodCallback 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_SetDeviceMethodCallback`](#iothub__client_8h_1a44acf1df96a838735870184172d2f783)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,`[`IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC`](#iothub__client__core__common_8h_1aa758c6c04994938fae9257289760d01a) deviceMethodCallback,void * userContextCallback)`

#### IoTHubClient_SetDeviceMethodCallback_Ex 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_SetDeviceMethodCallback_Ex`](#iothub__client_8h_1a3934d3b340ec1483d79acf34d1ea950f)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,`[`IOTHUB_CLIENT_INBOUND_DEVICE_METHOD_CALLBACK`](#iothub__client__core__common_8h_1a43072ecc913e5ca776108b1731553c30) inboundDeviceMethodCallback,void * userContextCallback)`

#### IoTHubClient_DeviceMethodResponse 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_DeviceMethodResponse`](#iothub__client_8h_1acab103052c5b960e285c7c5d76d8d28f)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,`[`METHOD_HANDLE`](#iothub__transport__ll_8h_1a1cc79695294f89e97fb945066a3b3d77) methodId,const unsigned char * response,size_t response_size,int statusCode)`

#### IoTHubClient_UploadToBlobAsync 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_UploadToBlobAsync`](#iothub__client_8h_1a969f7957eb536d89e35e6fac2e5c7d99)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,const char * destinationFileName,const unsigned char * source,size_t size,`[`IOTHUB_CLIENT_FILE_UPLOAD_CALLBACK`](#iothub__client__core__common_8h_1a039d574a949c85ba9c183c88d4ce03bf) iotHubClientFileUploadCallback,void * context)`

#### IoTHubClient_UploadMultipleBlocksToBlobAsync 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_UploadMultipleBlocksToBlobAsync`](#iothub__client_8h_1aa8e45112bb591d443cd8f71c98bd445e)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,const char * destinationFileName,`[`IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK`](#iothub__client__core__common_8h_1a188fa4251310dad00defabb8f77a292f) getDataCallback,void * context)`

#### IoTHubClient_UploadMultipleBlocksToBlobAsyncEx 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_UploadMultipleBlocksToBlobAsyncEx`](#iothub__client_8h_1a2e3c65d775ffa45a05b7e7052b3bc088)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,const char * destinationFileName,`[`IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK_EX`](#iothub__client__core__common_8h_1a0d9944dec4c4dd2bdd75cebb466dcf6c) getDataCallbackEx,void * context)`

