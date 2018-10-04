# Header file iothub_device_client_ll.h 

APIs that allow a user (usually a device) to communicate with an Azure IoTHub.

## Includes

\#include <stddef.h>  
\#include <stdint.h>  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include ["iothub_transport_ll.h"](iot-c-ref-iothub-transport-ll-h.md)  
\#include ["iothub_client_core_ll.h"](iot-c-ref-iothub-client-core-ll-h.md)  

## Detailed Description

IoTHubDeviceClient_LL is a module that allows a user (usually a device) to communicate with an Azure IoTHub. It can send events and receive messages. At any given moment in time there can only be at most 1 message callback function.

This API surface contains a set of APIs that allows the user to interact with the lower layer portion of the IoTHubClient. These APIs contain `_LL_` in their name, but retain the same functionality like the `IoTHubDeviceClient_`... APIs, with one difference. If the `_LL_` APIs are used then the user is responsible for scheduling when the actual work done by the IoTHubClient happens (when the data is sent/received on/from the wire). This is useful for constrained devices where spinning a separate thread is often not desired.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IoTHubDeviceClient_LL_CreateFromConnectionString](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-createfromconnectionstring.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using the specified connection string parameter.
[IoTHubDeviceClient_LL_Create](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-create.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using the specified parameters.
[IoTHubDeviceClient_LL_CreateWithTransport](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-createwithtransport.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using an existing transport.
[IoTHubDeviceClient_LL_CreateFromDeviceAuth](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-createfromdeviceauth.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using the device auth module.
[IoTHubDeviceClient_LL_Destroy](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-destroy.md)            | Disposes of resources allocated by the IoT Hub client. This is a blocking call.
[IoTHubDeviceClient_LL_SendEventAsync](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-sendeventasync.md)            | Asynchronous call to send the message specified by `eventMessageHandle`.
[IoTHubDeviceClient_LL_GetSendStatus](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-getsendstatus.md)            | This function returns the current sending status for IoTHubClient.
[IoTHubDeviceClient_LL_SetMessageCallback](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-setmessagecallback.md)            | Sets up the message callback to be invoked when IoT Hub issues a message to the device. This is a blocking call.
[IoTHubDeviceClient_LL_SetConnectionStatusCallback](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-setconnectionstatuscallback.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubDeviceClient_LL_SetRetryPolicy](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-setretrypolicy.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubDeviceClient_LL_GetRetryPolicy](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-getretrypolicy.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubDeviceClient_LL_GetLastMessageReceiveTime](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-getlastmessagereceivetime.md)            | This function returns in the out parameter `lastMessageReceiveTime` what was the value of the `time` function when the last message was received at the client.
[IoTHubDeviceClient_LL_DoWork](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-dowork.md)            | This function is meant to be called by the user when work (sending/receiving) can be done by the IoTHubClient.
[IoTHubDeviceClient_LL_SetOption](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-setoption.md)            | This API sets a runtime option identified by parameter `optionName` to a value pointed to by `value`. `optionName` and the data type `value` is pointing to are specific for every option.
[IoTHubDeviceClient_LL_SetDeviceTwinCallback](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-setdevicetwincallback.md)            | This API specifies a callback to be used when the device receives a desired state update.
[IoTHubDeviceClient_LL_SendReportedState](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-sendreportedstate.md)            | This API sends a report of the device's properties and their current values.
[IoTHubDeviceClient_LL_SetDeviceMethodCallback](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-setdevicemethodcallback.md)            | This API sets the callback for async cloud to device method calls.
[IoTHubDeviceClient_LL_DeviceMethodResponse](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-devicemethodresponse.md)            | This API responds to an asnyc method callback identified the methodId.
[IoTHubDeviceClient_LL_UploadToBlob](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-uploadtoblob.md)            | This API uploads to Azure Storage the content pointed to by `source` having the size `size` under the blob name devicename/.
[IoTHubDeviceClient_LL_UploadMultipleBlocksToBlob](./iot-c-ref-iothub-device-client-ll-h/iothubdeviceclient-ll-uploadmultipleblockstoblob.md)            | This API uploads to Azure Storage the content provided block by block by `getDataCallback` under the blob name devicename/.

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
IOTHUB_DEVICE_CLIENT_LL_HANDLE            | 

## Function documentation

#### IoTHubDeviceClient_LL_CreateFromConnectionString 
[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) `[`IoTHubDeviceClient_LL_CreateFromConnectionString`](#iothub__device__client__ll_8h_1a443f69aee79ac2c74d5983eb723c9f55)(const char * connectionString,`[`IOTHUB_CLIENT_TRANSPORT_PROVIDER`](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)`

#### IoTHubDeviceClient_LL_Create 
[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) `[`IoTHubDeviceClient_LL_Create`](#iothub__device__client__ll_8h_1ac98f962a67a3913f0fd483b1051ef37e)(const `[`IOTHUB_CLIENT_CONFIG`](#struct_i_o_t_h_u_b___c_l_i_e_n_t___c_o_n_f_i_g) * config)`

#### IoTHubDeviceClient_LL_CreateWithTransport 
[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) `[`IoTHubDeviceClient_LL_CreateWithTransport`](#iothub__device__client__ll_8h_1a044b4357c6a5450de02cf9c774dca87b)(const `[`IOTHUB_CLIENT_DEVICE_CONFIG`](#struct_i_o_t_h_u_b___c_l_i_e_n_t___d_e_v_i_c_e___c_o_n_f_i_g) * config)`

#### IoTHubDeviceClient_LL_CreateFromDeviceAuth 
[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) `[`IoTHubDeviceClient_LL_CreateFromDeviceAuth`](#iothub__device__client__ll_8h_1a0e84dff5ca26d7a915dcc61963db361e)(const char * iothub_uri,const char * device_id,`[`IOTHUB_CLIENT_TRANSPORT_PROVIDER`](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)`

#### IoTHubDeviceClient_LL_Destroy 
void `[`IoTHubDeviceClient_LL_Destroy`](#iothub__device__client__ll_8h_1ad2ac0d9176060dfeee0664668ce87e6f)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle)`

#### IoTHubDeviceClient_LL_SendEventAsync 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_SendEventAsync`](#iothub__device__client__ll_8h_1a56cfcb637e1f46cf0f5e6e2bb81457ad)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) eventMessageHandle,`[`IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK`](#iothub__client__core__common_8h_1a41b17fcb2cb70587e3576226561648a0) eventConfirmationCallback,void * userContextCallback)`

#### IoTHubDeviceClient_LL_GetSendStatus 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_GetSendStatus`](#iothub__device__client__ll_8h_1a3c4083b15ea124427a2846ba4608ba3e)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,`[`IOTHUB_CLIENT_STATUS`](#iothub__client__core__common_8h_1af80b6370369f3c1bb53399deccb4491c) * iotHubClientStatus)`

#### IoTHubDeviceClient_LL_SetMessageCallback 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_SetMessageCallback`](#iothub__device__client__ll_8h_1af8527e95987aa562dfbbf48482b78be1)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,`[`IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC`](#iothub__client__core__common_8h_1adf7097e8fc9e34f26dd9347d4eaa5f8d) messageCallback,void * userContextCallback)`

#### IoTHubDeviceClient_LL_SetConnectionStatusCallback 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_SetConnectionStatusCallback`](#iothub__device__client__ll_8h_1a6d7da21562bfbcef5aa9d38503002bb2)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,`[`IOTHUB_CLIENT_CONNECTION_STATUS_CALLBACK`](#iothub__client__core__common_8h_1ad0d7e0712e620b1d55e72652f4f4f560) connectionStatusCallback,void * userContextCallback)`

#### IoTHubDeviceClient_LL_SetRetryPolicy 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_SetRetryPolicy`](#iothub__device__client__ll_8h_1abb0e2ca40fc6786208b276e201de0b4c)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,`[`IOTHUB_CLIENT_RETRY_POLICY`](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) retryPolicy,size_t retryTimeoutLimitInSeconds)`

#### IoTHubDeviceClient_LL_GetRetryPolicy 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_GetRetryPolicy`](#iothub__device__client__ll_8h_1ae4c27fd75ae287332ce413b439b59cba)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,`[`IOTHUB_CLIENT_RETRY_POLICY`](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) * retryPolicy,size_t * retryTimeoutLimitInSeconds)`

#### IoTHubDeviceClient_LL_GetLastMessageReceiveTime 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_GetLastMessageReceiveTime`](#iothub__device__client__ll_8h_1a04d8f5acf6f66f0075e5febc4a43695c)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,time_t * lastMessageReceiveTime)`

#### IoTHubDeviceClient_LL_DoWork 
void `[`IoTHubDeviceClient_LL_DoWork`](#iothub__device__client__ll_8h_1a6e77da5502dff2bb43bace5173242f37)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle)`

#### IoTHubDeviceClient_LL_SetOption 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_SetOption`](#iothub__device__client__ll_8h_1a23a4b07e54e7e03668dc9f832cd06368)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,const char * optionName,const void * value)`

#### IoTHubDeviceClient_LL_SetDeviceTwinCallback 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_SetDeviceTwinCallback`](#iothub__device__client__ll_8h_1a347a0fb6822105b8ad0e59f856acd850)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,`[`IOTHUB_CLIENT_DEVICE_TWIN_CALLBACK`](#iothub__client__core__common_8h_1a3020471f05025405840d9c43466122dc) deviceTwinCallback,void * userContextCallback)`

#### IoTHubDeviceClient_LL_SendReportedState 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_SendReportedState`](#iothub__device__client__ll_8h_1a8809f6e5178212de109cfcfa02bce978)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,const unsigned char * reportedState,size_t size,`[`IOTHUB_CLIENT_REPORTED_STATE_CALLBACK`](#iothub__client__core__common_8h_1a9ae117da9222a5138e31a8953ce18bbc) reportedStateCallback,void * userContextCallback)`

#### IoTHubDeviceClient_LL_SetDeviceMethodCallback 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_SetDeviceMethodCallback`](#iothub__device__client__ll_8h_1aaaa00ed49441cf566eb94ded6182cab4)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,`[`IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC`](#iothub__client__core__common_8h_1aa758c6c04994938fae9257289760d01a) deviceMethodCallback,void * userContextCallback)`

#### IoTHubDeviceClient_LL_DeviceMethodResponse 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_DeviceMethodResponse`](#iothub__device__client__ll_8h_1ab7206293126c32eccb7e274d266d4c97)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,`[`METHOD_HANDLE`](#iothub__transport__ll_8h_1a1cc79695294f89e97fb945066a3b3d77) methodId,const unsigned char * response,size_t respSize,int statusCode)`

#### IoTHubDeviceClient_LL_UploadToBlob 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_UploadToBlob`](#iothub__device__client__ll_8h_1a1b8e1336348c641fc40750a5ca256c6d)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,const char * destinationFileName,const unsigned char * source,size_t size)`

#### IoTHubDeviceClient_LL_UploadMultipleBlocksToBlob 
[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubDeviceClient_LL_UploadMultipleBlocksToBlob`](#iothub__device__client__ll_8h_1a688c3982badc6412f7856b0e85bd4d60)(`[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,const char * destinationFileName,`[`IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK_EX`](#iothub__client__core__common_8h_1a0d9944dec4c4dd2bdd75cebb466dcf6c) getDataCallbackEx,void * context)`

