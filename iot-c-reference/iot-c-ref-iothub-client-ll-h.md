# Header file iothub_client_ll.h 

APIs that allow a user (usually a device) to communicate with an Azure IoTHub.

## Includes

\#include <stddef.h>  
\#include <stdint.h>  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include ["iothub_transport_ll.h"](iot-c-ref-iothub-transport-ll-h.md)  
\#include ["iothub_client_core_ll.h"](iot-c-ref-iothub-client-core-ll-h.md)  

## Detailed Description

IoTHubClient_LL is a module that allows a user (usually a device) to communicate with an Azure IoTHub. It can send events and receive messages. At any given moment in time there can only be at most 1 message callback function.

This API surface contains a set of APIs that allows the user to interact with the lower layer portion of the IoTHubClient. These APIs contain `_LL_` in their name, but retain the same functionality like the `IoTHubClient_`... APIs, with one difference. If the `_LL_` APIs are used then the user is responsible for scheduling when the actual work done by the IoTHubClient happens (when the data is sent/received on/from the wire). This is useful for constrained devices where spinning a separate thread is often not desired.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IoTHubClient_LL_CreateFromConnectionString](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-createfromconnectionstring.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using the specified connection string parameter.
[IoTHubClient_LL_Create](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-create.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using the specified parameters.
[IoTHubClient_LL_CreateWithTransport](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-createwithtransport.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using an existing transport.
[IoTHubClient_LL_CreateFromDeviceAuth](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-createfromdeviceauth.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using the device auth module.
[IoTHubClient_LL_Destroy](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-destroy.md)            | Disposes of resources allocated by the IoT Hub client. This is a blocking call.
[IoTHubClient_LL_SendEventAsync](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-sendeventasync.md)            | Asynchronous call to send the message specified by `eventMessageHandle`.
[IoTHubClient_LL_GetSendStatus](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-getsendstatus.md)            | This function returns the current sending status for IoTHubClient.
[IoTHubClient_LL_SetMessageCallback](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-setmessagecallback.md)            | Sets up the message callback to be invoked when IoT Hub issues a message to the device. This is a blocking call.
[IoTHubClient_LL_SetConnectionStatusCallback](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-setconnectionstatuscallback.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubClient_LL_SetRetryPolicy](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-setretrypolicy.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubClient_LL_GetRetryPolicy](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-getretrypolicy.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubClient_LL_GetLastMessageReceiveTime](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-getlastmessagereceivetime.md)            | This function returns in the out parameter `lastMessageReceiveTime` what was the value of the `time` function when the last message was received at the client.
[IoTHubClient_LL_DoWork](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-dowork.md)            | This function is meant to be called by the user when work (sending/receiving) can be done by the IoTHubClient.
[IoTHubClient_LL_SetOption](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-setoption.md)            | This API sets a runtime option identified by parameter `optionName` to a value pointed to by `value`. `optionName` and the data type `value` is pointing to are specific for every option.
[IoTHubClient_LL_SetDeviceTwinCallback](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-setdevicetwincallback.md)            | This API specifies a call back to be used when the device receives a desired state update.
[IoTHubClient_LL_SendReportedState](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-sendreportedstate.md)            | This API sneds a report of the device's properties and their current values.
[IoTHubClient_LL_SetDeviceMethodCallback](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-setdevicemethodcallback.md)            | This API sets callback for cloud to device method call.
[IoTHubClient_LL_SetDeviceMethodCallback_Ex](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-setdevicemethodcallback-ex.md)            | This API sets callback for async cloud to device method call.
[IoTHubClient_LL_DeviceMethodResponse](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-devicemethodresponse.md)            | This API responses to a asnyc method callback identified the methodId.
[IoTHubClient_LL_UploadToBlob](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-uploadtoblob.md)            | This API uploads to Azure Storage the content pointed to by `source` having the size `size` under the blob name devicename/.
[IoTHubClient_LL_UploadMultipleBlocksToBlob](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-uploadmultipleblockstoblob.md)            | This API uploads to Azure Storage the content provided block by block by `getDataCallback` under the blob name devicename/.
[IoTHubClient_LL_UploadMultipleBlocksToBlobEx](./iot-c-ref-iothub-client-ll-h/iothubclient-ll-uploadmultipleblockstoblobex.md)            | This API uploads to Azure Storage the content provided block by block by `getDataCallback` under the blob name devicename/.

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
IOTHUB_CLIENT_LL_HANDLE            | 

## Function documentation

#### IoTHubClient_LL_CreateFromConnectionString 
[IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) [IoTHubClient_LL_CreateFromConnectionString](#iothub__client__ll_8h_1aadecae0b07958725e83cae943250469d)(const char * connectionString,[IOTHUB_CLIENT_TRANSPORT_PROVIDER](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)

#### IoTHubClient_LL_Create 
[IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) [IoTHubClient_LL_Create](#iothub__client__ll_8h_1ad236a781c7fb988216b98be099125447)(const [IOTHUB_CLIENT_CONFIG](#struct_i_o_t_h_u_b___c_l_i_e_n_t___c_o_n_f_i_g) * config)

#### IoTHubClient_LL_CreateWithTransport 
[IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) [IoTHubClient_LL_CreateWithTransport](#iothub__client__ll_8h_1a5f2ea7dfbb5eeb2510e39a43c92fe61e)(const [IOTHUB_CLIENT_DEVICE_CONFIG](#struct_i_o_t_h_u_b___c_l_i_e_n_t___d_e_v_i_c_e___c_o_n_f_i_g) * config)

#### IoTHubClient_LL_CreateFromDeviceAuth 
[IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) [IoTHubClient_LL_CreateFromDeviceAuth](#iothub__client__ll_8h_1aeccf0188b7a31fa475383eb44328f6d9)(const char * iothub_uri,const char * device_id,[IOTHUB_CLIENT_TRANSPORT_PROVIDER](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)

#### IoTHubClient_LL_Destroy 
void [IoTHubClient_LL_Destroy](#iothub__client__ll_8h_1afc3049dc24e311713ab4735873989a4a)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle)

#### IoTHubClient_LL_SendEventAsync 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_SendEventAsync](#iothub__client__ll_8h_1ab47deec96944dd3f1bf0e747ab565277)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,[IOTHUB_MESSAGE_HANDLE](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) eventMessageHandle,[IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK](#iothub__client__core__common_8h_1a41b17fcb2cb70587e3576226561648a0) eventConfirmationCallback,void * userContextCallback)

#### IoTHubClient_LL_GetSendStatus 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_GetSendStatus](#iothub__client__ll_8h_1aa7773cdda101288cfd805c34f726eb84)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,[IOTHUB_CLIENT_STATUS](#iothub__client__core__common_8h_1af80b6370369f3c1bb53399deccb4491c) * iotHubClientStatus)

#### IoTHubClient_LL_SetMessageCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_SetMessageCallback](#iothub__client__ll_8h_1af8c8a00af8c2fac1ccf2111eb4e2016c)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,[IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC](#iothub__client__core__common_8h_1adf7097e8fc9e34f26dd9347d4eaa5f8d) messageCallback,void * userContextCallback)

#### IoTHubClient_LL_SetConnectionStatusCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_SetConnectionStatusCallback](#iothub__client__ll_8h_1a6d0656a868fcbdaba0fba066fbe92bd9)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,[IOTHUB_CLIENT_CONNECTION_STATUS_CALLBACK](#iothub__client__core__common_8h_1ad0d7e0712e620b1d55e72652f4f4f560) connectionStatusCallback,void * userContextCallback)

#### IoTHubClient_LL_SetRetryPolicy 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_SetRetryPolicy](#iothub__client__ll_8h_1a8a0b5a41fae26b16aa01134d09e93278)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,[IOTHUB_CLIENT_RETRY_POLICY](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) retryPolicy,size_t retryTimeoutLimitInSeconds)

#### IoTHubClient_LL_GetRetryPolicy 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_GetRetryPolicy](#iothub__client__ll_8h_1acd507eebe67d0b08bf49838120d9d3db)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,[IOTHUB_CLIENT_RETRY_POLICY](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) * retryPolicy,size_t * retryTimeoutLimitInSeconds)

#### IoTHubClient_LL_GetLastMessageReceiveTime 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_GetLastMessageReceiveTime](#iothub__client__ll_8h_1a21b712300499f014b8c467e195f2503c)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,time_t * lastMessageReceiveTime)

#### IoTHubClient_LL_DoWork 
void [IoTHubClient_LL_DoWork](#iothub__client__ll_8h_1af5e5e122bdc1f1228ae2116fc158b3d6)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle)

#### IoTHubClient_LL_SetOption 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_SetOption](#iothub__client__ll_8h_1a70eb58c7ede92f75001104ff4745faa2)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,const char * optionName,const void * value)

#### IoTHubClient_LL_SetDeviceTwinCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_SetDeviceTwinCallback](#iothub__client__ll_8h_1ac7df62eaef41c0081af988467e45a0e4)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,[IOTHUB_CLIENT_DEVICE_TWIN_CALLBACK](#iothub__client__core__common_8h_1a3020471f05025405840d9c43466122dc) deviceTwinCallback,void * userContextCallback)

#### IoTHubClient_LL_SendReportedState 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_SendReportedState](#iothub__client__ll_8h_1af48d8760649bf7792d861874e89e6b66)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,const unsigned char * reportedState,size_t size,[IOTHUB_CLIENT_REPORTED_STATE_CALLBACK](#iothub__client__core__common_8h_1a9ae117da9222a5138e31a8953ce18bbc) reportedStateCallback,void * userContextCallback)

#### IoTHubClient_LL_SetDeviceMethodCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_SetDeviceMethodCallback](#iothub__client__ll_8h_1ae7a7582ea0ea061418f21bab3d236a1d)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,[IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC](#iothub__client__core__common_8h_1aa758c6c04994938fae9257289760d01a) deviceMethodCallback,void * userContextCallback)

#### IoTHubClient_LL_SetDeviceMethodCallback_Ex 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_SetDeviceMethodCallback_Ex](#iothub__client__ll_8h_1a93d4fa3242a15429e6cf6e0d7c65da9e)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,[IOTHUB_CLIENT_INBOUND_DEVICE_METHOD_CALLBACK](#iothub__client__core__common_8h_1a43072ecc913e5ca776108b1731553c30) inboundDeviceMethodCallback,void * userContextCallback)

#### IoTHubClient_LL_DeviceMethodResponse 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_DeviceMethodResponse](#iothub__client__ll_8h_1af2e62eff3e74c553bf75a4a13f054f63)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,[METHOD_HANDLE](#iothub__transport__ll_8h_1a1cc79695294f89e97fb945066a3b3d77) methodId,const unsigned char * response,size_t respSize,int statusCode)

#### IoTHubClient_LL_UploadToBlob 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_UploadToBlob](#iothub__client__ll_8h_1a60f63e1839e2386233b7fee6d3a9f60a)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,const char * destinationFileName,const unsigned char * source,size_t size)

#### IoTHubClient_LL_UploadMultipleBlocksToBlob 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_UploadMultipleBlocksToBlob](#iothub__client__ll_8h_1a1720e09a7d7bc17bcdfaf4612d51b061)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,const char * destinationFileName,[IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK](#iothub__client__core__common_8h_1a188fa4251310dad00defabb8f77a292f) getDataCallback,void * context)

#### IoTHubClient_LL_UploadMultipleBlocksToBlobEx 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_UploadMultipleBlocksToBlobEx](#iothub__client__ll_8h_1a50f1eb59b79f731ca8c6d63cef9f625f)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,const char * destinationFileName,[IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK_EX](#iothub__client__core__common_8h_1a0d9944dec4c4dd2bdd75cebb466dcf6c) getDataCallbackEx,void * context)

