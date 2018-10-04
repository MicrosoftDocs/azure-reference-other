# Header file iothub_client_core.h 

Extends the IoTHubClientCore_LL module with additional features.

## Includes

\#include <stddef.h>  
\#include <stdint.h>  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include ["iothub_client_core_ll.h"](iot-c-ref-iothub-client-core-ll-h.md)  

## Detailed Description

IoTHubClientCore is a module that extends the IoTHubClientCore_LL module with 2 features:

* scheduling the work for the IoTHubCLient from a thread, so that the user does not need to create their own thread

* thread-safe APIs

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IoTHubClientCore_CreateFromConnectionString](./iot-c-ref-iothub-client-core-h/iothubclientcore-createfromconnectionstring.md)            | 
[IoTHubClientCore_Create](./iot-c-ref-iothub-client-core-h/iothubclientcore-create.md)            | 
[IoTHubClientCore_CreateWithTransport](./iot-c-ref-iothub-client-core-h/iothubclientcore-createwithtransport.md)            | 
[IoTHubClientCore_CreateFromDeviceAuth](./iot-c-ref-iothub-client-core-h/iothubclientcore-createfromdeviceauth.md)            | 
[IoTHubClientCore_Destroy](./iot-c-ref-iothub-client-core-h/iothubclientcore-destroy.md)            | 
[IoTHubClientCore_SendEventAsync](./iot-c-ref-iothub-client-core-h/iothubclientcore-sendeventasync.md)            | 
[IoTHubClientCore_GetSendStatus](./iot-c-ref-iothub-client-core-h/iothubclientcore-getsendstatus.md)            | 
[IoTHubClientCore_SetMessageCallback](./iot-c-ref-iothub-client-core-h/iothubclientcore-setmessagecallback.md)            | 
[IoTHubClientCore_SetConnectionStatusCallback](./iot-c-ref-iothub-client-core-h/iothubclientcore-setconnectionstatuscallback.md)            | 
[IoTHubClientCore_SetRetryPolicy](./iot-c-ref-iothub-client-core-h/iothubclientcore-setretrypolicy.md)            | 
[IoTHubClientCore_GetRetryPolicy](./iot-c-ref-iothub-client-core-h/iothubclientcore-getretrypolicy.md)            | 
[IoTHubClientCore_GetLastMessageReceiveTime](./iot-c-ref-iothub-client-core-h/iothubclientcore-getlastmessagereceivetime.md)            | 
[IoTHubClientCore_SetOption](./iot-c-ref-iothub-client-core-h/iothubclientcore-setoption.md)            | 
[IoTHubClientCore_SetDeviceTwinCallback](./iot-c-ref-iothub-client-core-h/iothubclientcore-setdevicetwincallback.md)            | 
[IoTHubClientCore_SendReportedState](./iot-c-ref-iothub-client-core-h/iothubclientcore-sendreportedstate.md)            | 
[IoTHubClientCore_SetDeviceMethodCallback](./iot-c-ref-iothub-client-core-h/iothubclientcore-setdevicemethodcallback.md)            | 
[IoTHubClientCore_SetDeviceMethodCallback_Ex](./iot-c-ref-iothub-client-core-h/iothubclientcore-setdevicemethodcallback-ex.md)            | 
[IoTHubClientCore_DeviceMethodResponse](./iot-c-ref-iothub-client-core-h/iothubclientcore-devicemethodresponse.md)            | 
[IoTHubClientCore_UploadToBlobAsync](./iot-c-ref-iothub-client-core-h/iothubclientcore-uploadtoblobasync.md)            | 
[IoTHubClientCore_UploadMultipleBlocksToBlobAsync](./iot-c-ref-iothub-client-core-h/iothubclientcore-uploadmultipleblockstoblobasync.md)            | 
[IoTHubClientCore_SendEventToOutputAsync](./iot-c-ref-iothub-client-core-h/iothubclientcore-sendeventtooutputasync.md)            | 
[IoTHubClientCore_SetInputMessageCallback](./iot-c-ref-iothub-client-core-h/iothubclientcore-setinputmessagecallback.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IOTHUB_CLIENT_CORE_INSTANCE_TYPE            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
IOTHUB_CLIENT_CORE_HANDLE            | 

## Function documentation

#### IoTHubClientCore_CreateFromConnectionString 
[IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) [IoTHubClientCore_CreateFromConnectionString](#iothub__client__core_8h_1a795076eefe5d2fe6a3693413d958be95)(const char * connectionString,[IOTHUB_CLIENT_TRANSPORT_PROVIDER](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)

#### IoTHubClientCore_Create 
[IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) [IoTHubClientCore_Create](#iothub__client__core_8h_1a5dd36dcb0cf449f4092f1896b350c68e)(const [IOTHUB_CLIENT_CONFIG](#struct_i_o_t_h_u_b___c_l_i_e_n_t___c_o_n_f_i_g) * config)

#### IoTHubClientCore_CreateWithTransport 
[IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) [IoTHubClientCore_CreateWithTransport](#iothub__client__core_8h_1a3fdc338f8b338abbdc4b715f197dede8)([TRANSPORT_HANDLE](#iothub__transport__ll_8h_1a085a6035b065e4f48f3789e428235aa4) transportHandle,const [IOTHUB_CLIENT_CONFIG](#struct_i_o_t_h_u_b___c_l_i_e_n_t___c_o_n_f_i_g) * config)

#### IoTHubClientCore_CreateFromDeviceAuth 
[IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) [IoTHubClientCore_CreateFromDeviceAuth](#iothub__client__core_8h_1ab466da7c64538de6de96f0a2a047886b)(const char * iothub_uri,const char * device_id,[IOTHUB_CLIENT_TRANSPORT_PROVIDER](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)

#### IoTHubClientCore_Destroy 
void [IoTHubClientCore_Destroy](#iothub__client__core_8h_1aac27cf00344d553f141eb67e2b1f898f)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle)

#### IoTHubClientCore_SendEventAsync 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_SendEventAsync](#iothub__client__core_8h_1a473269f7d3127ab54d1452ebcdfeb833)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,[IOTHUB_MESSAGE_HANDLE](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) eventMessageHandle,[IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK](#iothub__client__core__common_8h_1a41b17fcb2cb70587e3576226561648a0) eventConfirmationCallback,void * userContextCallback)

#### IoTHubClientCore_GetSendStatus 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_GetSendStatus](#iothub__client__core_8h_1a4bbdbb37a335729e83acda800d6f6417)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,[IOTHUB_CLIENT_STATUS](#iothub__client__core__common_8h_1af80b6370369f3c1bb53399deccb4491c) * iotHubClientStatus)

#### IoTHubClientCore_SetMessageCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_SetMessageCallback](#iothub__client__core_8h_1a8d70c7832de075343f6d66d9c884f3cd)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,[IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC](#iothub__client__core__common_8h_1adf7097e8fc9e34f26dd9347d4eaa5f8d) messageCallback,void * userContextCallback)

#### IoTHubClientCore_SetConnectionStatusCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_SetConnectionStatusCallback](#iothub__client__core_8h_1a41ca86fb2e54b4553a56c58e932b67e7)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,[IOTHUB_CLIENT_CONNECTION_STATUS_CALLBACK](#iothub__client__core__common_8h_1ad0d7e0712e620b1d55e72652f4f4f560) connectionStatusCallback,void * userContextCallback)

#### IoTHubClientCore_SetRetryPolicy 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_SetRetryPolicy](#iothub__client__core_8h_1a435d705c7f7c04d678b271221d7ff290)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,[IOTHUB_CLIENT_RETRY_POLICY](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) retryPolicy,size_t retryTimeoutLimitInSeconds)

#### IoTHubClientCore_GetRetryPolicy 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_GetRetryPolicy](#iothub__client__core_8h_1aa3c73573d427301c0b5c3cdaf0eb132b)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,[IOTHUB_CLIENT_RETRY_POLICY](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) * retryPolicy,size_t * retryTimeoutLimitInSeconds)

#### IoTHubClientCore_GetLastMessageReceiveTime 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_GetLastMessageReceiveTime](#iothub__client__core_8h_1a366e2047310b85c25d73e88d0c8a7f5e)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,time_t * lastMessageReceiveTime)

#### IoTHubClientCore_SetOption 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_SetOption](#iothub__client__core_8h_1a6e7605155d180064aca4a119f42ece66)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,const char * optionName,const void * value)

#### IoTHubClientCore_SetDeviceTwinCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_SetDeviceTwinCallback](#iothub__client__core_8h_1a2e3ee15378c46bfd437d4aa40904a861)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,[IOTHUB_CLIENT_DEVICE_TWIN_CALLBACK](#iothub__client__core__common_8h_1a3020471f05025405840d9c43466122dc) deviceTwinCallback,void * userContextCallback)

#### IoTHubClientCore_SendReportedState 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_SendReportedState](#iothub__client__core_8h_1af2d2c7154e6eda00ce4acbcb45f4f795)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,const unsigned char * reportedState,size_t size,[IOTHUB_CLIENT_REPORTED_STATE_CALLBACK](#iothub__client__core__common_8h_1a9ae117da9222a5138e31a8953ce18bbc) reportedStateCallback,void * userContextCallback)

#### IoTHubClientCore_SetDeviceMethodCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_SetDeviceMethodCallback](#iothub__client__core_8h_1a39fcf1c51943b9d193d89ca16b43aef1)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,[IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC](#iothub__client__core__common_8h_1aa758c6c04994938fae9257289760d01a) deviceMethodCallback,void * userContextCallback)

#### IoTHubClientCore_SetDeviceMethodCallback_Ex 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_SetDeviceMethodCallback_Ex](#iothub__client__core_8h_1ab455500ab26d0f558347b94102c25b63)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,[IOTHUB_CLIENT_INBOUND_DEVICE_METHOD_CALLBACK](#iothub__client__core__common_8h_1a43072ecc913e5ca776108b1731553c30) inboundDeviceMethodCallback,void * userContextCallback)

#### IoTHubClientCore_DeviceMethodResponse 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_DeviceMethodResponse](#iothub__client__core_8h_1a1caa672eb4fe863667d5b462684806db)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,[METHOD_HANDLE](#iothub__transport__ll_8h_1a1cc79695294f89e97fb945066a3b3d77) methodId,const unsigned char * response,size_t response_size,int statusCode)

#### IoTHubClientCore_UploadToBlobAsync 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_UploadToBlobAsync](#iothub__client__core_8h_1aedb911c89ed2211a68a6a5caae864384)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,const char * destinationFileName,const unsigned char * source,size_t size,[IOTHUB_CLIENT_FILE_UPLOAD_CALLBACK](#iothub__client__core__common_8h_1a039d574a949c85ba9c183c88d4ce03bf) iotHubClientFileUploadCallback,void * context)

#### IoTHubClientCore_UploadMultipleBlocksToBlobAsync 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_UploadMultipleBlocksToBlobAsync](#iothub__client__core_8h_1a4f71a1f122407ba049e30b4601ff5abe)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,const char * destinationFileName,[IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK](#iothub__client__core__common_8h_1a188fa4251310dad00defabb8f77a292f) getDataCallback,[IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK_EX](#iothub__client__core__common_8h_1a0d9944dec4c4dd2bdd75cebb466dcf6c) getDataCallbackEx,void * context)

#### IoTHubClientCore_SendEventToOutputAsync 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_SendEventToOutputAsync](#iothub__client__core_8h_1af53d52d778b39476600c76f9f031a435)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,[IOTHUB_MESSAGE_HANDLE](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) eventMessageHandle,const char * outputName,[IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK](#iothub__client__core__common_8h_1a41b17fcb2cb70587e3576226561648a0) eventConfirmationCallback,void * userContextCallback)

#### IoTHubClientCore_SetInputMessageCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClientCore_SetInputMessageCallback](#iothub__client__core_8h_1ae50dd38c6521293419a3148ec9a73356)([IOTHUB_CLIENT_CORE_HANDLE](#iothub__client__core_8h_1a1603e5baaf9b735a48bbfd0a4c3effb2) iotHubClientHandle,const char * inputName,[IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC](#iothub__client__core__common_8h_1adf7097e8fc9e34f26dd9347d4eaa5f8d) eventHandlerCallback,void * userContextCallback)

