# Header file iothub_client_core_ll.h 

APIs that allow a user (usually a device) to communicate with an Azure IoTHub.

## Includes

\#include <time.h>  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include ["iothub_transport_ll.h"](iot-c-ref-iothub-transport-ll-h.md)  
\#include ["iothub_client_core_common.h"](iot-c-ref-iothub-client-core-common-h.md)  

## Detailed Description

IoTHubClientCore_LL is a module that allows a user (usually a device) to communicate with an Azure IoTHub. It can send events and receive messages. At any given moment in time there can only be at most 1 message callback function.

This API surface contains a set of APIs that allows the user to interact with the lower layer portion of the IoTHubClient. These APIs contain `_LL_` in their name, but retain the same functionality like the `IoTHubClient_`... APIs, with one difference. If the `_LL_` APIs are used then the user is responsible for scheduling when the actual work done by the IoTHubClient happens (when the data is sent/received on/from the wire). This is useful for constrained devices where spinning a separate thread is often not desired.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IoTHubClientCore_LL_CreateFromConnectionString](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-createfromconnectionstring.md)            | 
[IoTHubClientCore_LL_Create](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-create.md)            | 
[IoTHubClientCore_LL_CreateWithTransport](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-createwithtransport.md)            | 
[IoTHubClientCore_LL_CreateFromDeviceAuth](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-createfromdeviceauth.md)            | 
[IoTHubClientCore_LL_Destroy](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-destroy.md)            | 
[IoTHubClientCore_LL_SendEventAsync](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-sendeventasync.md)            | 
[IoTHubClientCore_LL_GetSendStatus](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-getsendstatus.md)            | 
[IoTHubClientCore_LL_SetMessageCallback](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-setmessagecallback.md)            | 
[IoTHubClientCore_LL_SetConnectionStatusCallback](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-setconnectionstatuscallback.md)            | 
[IoTHubClientCore_LL_SetRetryPolicy](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-setretrypolicy.md)            | 
[IoTHubClientCore_LL_GetRetryPolicy](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-getretrypolicy.md)            | 
[IoTHubClientCore_LL_GetLastMessageReceiveTime](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-getlastmessagereceivetime.md)            | 
[IoTHubClientCore_LL_DoWork](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-dowork.md)            | 
[IoTHubClientCore_LL_SetOption](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-setoption.md)            | 
[IoTHubClientCore_LL_SetDeviceTwinCallback](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-setdevicetwincallback.md)            | 
[IoTHubClientCore_LL_SendReportedState](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-sendreportedstate.md)            | 
[IoTHubClientCore_LL_SetDeviceMethodCallback](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-setdevicemethodcallback.md)            | 
[IoTHubClientCore_LL_SetDeviceMethodCallback_Ex](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-setdevicemethodcallback-ex.md)            | 
[IoTHubClientCore_LL_DeviceMethodResponse](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-devicemethodresponse.md)            | 
[IoTHubClientCore_LL_SendEventToOutputAsync](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-sendeventtooutputasync.md)            | 
[IoTHubClientCore_LL_SetInputMessageCallback](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-setinputmessagecallback.md)            | 
[IoTHubClientCore_LL_UploadToBlob](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-uploadtoblob.md)            | 
[IoTHubClientCore_LL_UploadMultipleBlocksToBlob](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-uploadmultipleblockstoblob.md)            | 
[IoTHubClientCore_LL_UploadMultipleBlocksToBlobEx](./iot-c-ref-iothub-client-core-ll-h/iothubclientcore-ll-uploadmultipleblockstoblobex.md)            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
IOTHUB_CLIENT_CORE_LL_HANDLE            | 

## Function documentation

#### IoTHubClientCore_LL_CreateFromConnectionString 
[IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) [IoTHubClientCore_LL_CreateFromConnectionString](#iothub__client__core__ll_8h_1a3a1c1d3cfed1ef3de6e0749b298d4162)(const char * connectionString,[IOTHUB_CLIENT_TRANSPORT_PROVIDER](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)

#### IoTHubClientCore_LL_Create 
[IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) [IoTHubClientCore_LL_Create](#iothub__client__core__ll_8h_1a8bfba0d37ed08b5467515f74ef7556f4)(const [IOTHUB_CLIENT_CONFIG](#struct_i_o_t_h_u_b___c_l_i_e_n_t___c_o_n_f_i_g) * config)

#### IoTHubClientCore_LL_CreateWithTransport 
[IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) [IoTHubClientCore_LL_CreateWithTransport](#iothub__client__core__ll_8h_1add0e81dcad9db0009609c156abb5d171)(const [IOTHUB_CLIENT_DEVICE_CONFIG](#struct_i_o_t_h_u_b___c_l_i_e_n_t___d_e_v_i_c_e___c_o_n_f_i_g) * config)

#### IoTHubClientCore_LL_CreateFromDeviceAuth 
[IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) [IoTHubClientCore_LL_CreateFromDeviceAuth](#iothub__client__core__ll_8h_1a3e5f344a82ce6ce329dfe2b7713bded8)(const char * iothub_uri,const char * device_id,[IOTHUB_CLIENT_TRANSPORT_PROVIDER](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)

#### IoTHubClientCore_LL_Destroy 
void [IoTHubClientCore_LL_Destroy](#iothub__client__core__ll_8h_1a68c72f4aec17c8e35971eebe2163794f)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle)

#### IoTHubClientCore_LL_SendEventAsync 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_SendEventAsync](#iothub__client__core__ll_8h_1ae88a6be21b3d337c45cd29b970f6bd88)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,[IOTHUB_MESSAGE_HANDLE](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) eventMessageHandle,[IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK](#iothub__client__core__common_8h_1a41b17fcb2cb70587e3576226561648a0) eventConfirmationCallback,void * userContextCallback)

#### IoTHubClientCore_LL_GetSendStatus 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_GetSendStatus](#iothub__client__core__ll_8h_1ae4f9df7b4a229c15ce490266043505d7)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,[IOTHUB_CLIENT_STATUS](#iothub__client__core__common_8h_1af80b6370369f3c1bb53399deccb4491c) * iotHubClientStatus)

#### IoTHubClientCore_LL_SetMessageCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_SetMessageCallback](#iothub__client__core__ll_8h_1adf7d7cf85822f7d7c3f82acf918de4fe)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,[IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC](#iothub__client__core__common_8h_1adf7097e8fc9e34f26dd9347d4eaa5f8d) messageCallback,void * userContextCallback)

#### IoTHubClientCore_LL_SetConnectionStatusCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_SetConnectionStatusCallback](#iothub__client__core__ll_8h_1a55c3b9451c3500201e18601e189ba18f)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,[IOTHUB_CLIENT_CONNECTION_STATUS_CALLBACK](#iothub__client__core__common_8h_1ad0d7e0712e620b1d55e72652f4f4f560) connectionStatusCallback,void * userContextCallback)

#### IoTHubClientCore_LL_SetRetryPolicy 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_SetRetryPolicy](#iothub__client__core__ll_8h_1a338ef56c513b51aba5e77ccb7ede4f91)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,[IOTHUB_CLIENT_RETRY_POLICY](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) retryPolicy,size_t retryTimeoutLimitInSeconds)

#### IoTHubClientCore_LL_GetRetryPolicy 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_GetRetryPolicy](#iothub__client__core__ll_8h_1a27c38c07f610cf5ed2cb004b547462ec)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,[IOTHUB_CLIENT_RETRY_POLICY](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) * retryPolicy,size_t * retryTimeoutLimitInSeconds)

#### IoTHubClientCore_LL_GetLastMessageReceiveTime 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_GetLastMessageReceiveTime](#iothub__client__core__ll_8h_1ad1d17eb7a1a441bc520b7c17dd45a975)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,time_t * lastMessageReceiveTime)

#### IoTHubClientCore_LL_DoWork 
void [IoTHubClientCore_LL_DoWork](#iothub__client__core__ll_8h_1ad0c88549cf91627422ce5757e7e1ef24)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle)

#### IoTHubClientCore_LL_SetOption 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_SetOption](#iothub__client__core__ll_8h_1a2a6eb495ce3dcfb3974f258ff9de5eb9)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,const char * optionName,const void * value)

#### IoTHubClientCore_LL_SetDeviceTwinCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_SetDeviceTwinCallback](#iothub__client__core__ll_8h_1af1891223c6f6644d838b53f827d6bc9f)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,[IOTHUB_CLIENT_DEVICE_TWIN_CALLBACK](#iothub__client__core__common_8h_1a3020471f05025405840d9c43466122dc) deviceTwinCallback,void * userContextCallback)

#### IoTHubClientCore_LL_SendReportedState 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_SendReportedState](#iothub__client__core__ll_8h_1a59d78494afc06a979131994246ed7994)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,const unsigned char * reportedState,size_t size,[IOTHUB_CLIENT_REPORTED_STATE_CALLBACK](#iothub__client__core__common_8h_1a9ae117da9222a5138e31a8953ce18bbc) reportedStateCallback,void * userContextCallback)

#### IoTHubClientCore_LL_SetDeviceMethodCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_SetDeviceMethodCallback](#iothub__client__core__ll_8h_1a0988ca17bb8733a9c426941341e24ac3)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,[IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC](#iothub__client__core__common_8h_1aa758c6c04994938fae9257289760d01a) deviceMethodCallback,void * userContextCallback)

#### IoTHubClientCore_LL_SetDeviceMethodCallback_Ex 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_SetDeviceMethodCallback_Ex](#iothub__client__core__ll_8h_1a5e3bb256c2c210a9c9fb052204d00c5e)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,[IOTHUB_CLIENT_INBOUND_DEVICE_METHOD_CALLBACK](#iothub__client__core__common_8h_1a43072ecc913e5ca776108b1731553c30) inboundDeviceMethodCallback,void * userContextCallback)

#### IoTHubClientCore_LL_DeviceMethodResponse 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_DeviceMethodResponse](#iothub__client__core__ll_8h_1a6d748573a00f8b890abee91d0ef4ec49)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,[METHOD_HANDLE](#iothub__transport__ll_8h_1a1cc79695294f89e97fb945066a3b3d77) methodId,const unsigned char * response,size_t respSize,int statusCode)

#### IoTHubClientCore_LL_SendEventToOutputAsync 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_SendEventToOutputAsync](#iothub__client__core__ll_8h_1ac35593d70f2ff42e67ad937d700b9138)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,[IOTHUB_MESSAGE_HANDLE](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) eventMessageHandle,const char * outputName,[IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK](#iothub__client__core__common_8h_1a41b17fcb2cb70587e3576226561648a0) eventConfirmationCallback,void * userContextCallback)

#### IoTHubClientCore_LL_SetInputMessageCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_SetInputMessageCallback](#iothub__client__core__ll_8h_1a2eb99c14ec5573c681762ad392cf5039)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,const char * inputName,[IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC](#iothub__client__core__common_8h_1adf7097e8fc9e34f26dd9347d4eaa5f8d) eventHandlerCallback,void * userContextCallback)

#### IoTHubClientCore_LL_UploadToBlob 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_UploadToBlob](#iothub__client__core__ll_8h_1aa0ce287be0b5da90af8d60f6165355ed)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,const char * destinationFileName,const unsigned char * source,size_t size)

#### IoTHubClientCore_LL_UploadMultipleBlocksToBlob 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_UploadMultipleBlocksToBlob](#iothub__client__core__ll_8h_1a34e1ad7d3d78433d9dc53dd72f586bd2)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,const char * destinationFileName,[IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK](#iothub__client__core__common_8h_1a188fa4251310dad00defabb8f77a292f) getDataCallback,void * context)

#### IoTHubClientCore_LL_UploadMultipleBlocksToBlobEx 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_LL_UploadMultipleBlocksToBlobEx](#iothub__client__core__ll_8h_1a1fb409f253995ad834038994abed55b0)([IOTHUB_CLIENT_CORE_LL_HANDLE](#iothub__client__core__ll_8h_1ad22c09a66c46ae2f464825eb7acd72d8) iotHubClientHandle,const char * destinationFileName,[IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK_EX](#iothub__client__core__common_8h_1a0d9944dec4c4dd2bdd75cebb466dcf6c) getDataCallbackEx,void * context)

