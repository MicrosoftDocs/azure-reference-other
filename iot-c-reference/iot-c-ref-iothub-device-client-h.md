# Header file iothub_device_client.h 

Extends the IoTHubCLient_LL module with additional features.

## Includes

\#include <stddef.h>  
\#include <stdint.h>  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include ["iothub_transport_ll.h"](iot-c-ref-iothub-transport-ll-h.md)  
\#include ["iothub_client_core_ll.h"](iot-c-ref-iothub-client-core-ll-h.md)  
\#include ["iothub_client_core.h"](iot-c-ref-iothub-client-core-h.md)  
\#include ["iothub_device_client_ll.h"](iot-c-ref-iothub-device-client-ll-h.md)  

## Detailed Description

IoTHubClient is a module that extends the IoTHubCLient_LL module with 2 features:

* scheduling the work for the IoTHubCLient from a thread, so that the user does not need to create their own thread

* thread-safe APIs

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IoTHubDeviceClient_CreateFromConnectionString](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-createfromconnectionstring.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using the specified connection string parameter.
[IoTHubDeviceClient_Create](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-create.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using the specified parameters.
[IoTHubDeviceClient_CreateWithTransport](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-createwithtransport.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using the specified parameters.
[IoTHubDeviceClient_CreateFromDeviceAuth](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-createfromdeviceauth.md)            | Creates a IoT Hub client for communication with an existing IoT Hub using the device auth module.
[IoTHubDeviceClient_Destroy](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-destroy.md)            | Disposes of resources allocated by the IoT Hub client. This is a blocking call.
[IoTHubDeviceClient_SendEventAsync](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-sendeventasync.md)            | Asynchronous call to send the message specified by `eventMessageHandle`.
[IoTHubDeviceClient_GetSendStatus](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-getsendstatus.md)            | This function returns the current sending status for IoTHubClient.
[IoTHubDeviceClient_SetMessageCallback](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-setmessagecallback.md)            | Sets up the message callback to be invoked when IoT Hub issues a message to the device. This is a blocking call.
[IoTHubDeviceClient_SetConnectionStatusCallback](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-setconnectionstatuscallback.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubDeviceClient_SetRetryPolicy](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-setretrypolicy.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubDeviceClient_GetRetryPolicy](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-getretrypolicy.md)            | Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.
[IoTHubDeviceClient_GetLastMessageReceiveTime](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-getlastmessagereceivetime.md)            | This function returns in the out parameter `lastMessageReceiveTime` what was the value of the `time` function when the last message was received at the client.
[IoTHubDeviceClient_SetOption](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-setoption.md)            | This API sets a runtime option identified by parameter `optionName` to a value pointed to by `value`. `optionName` and the data type `value` is pointing to are specific for every option.
[IoTHubDeviceClient_SetDeviceTwinCallback](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-setdevicetwincallback.md)            | This API specifies a callback to be used when the device receives a state update.
[IoTHubDeviceClient_SendReportedState](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-sendreportedstate.md)            | This API sends a report of the device's properties and their current values.
[IoTHubDeviceClient_SetDeviceMethodCallback](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-setdevicemethodcallback.md)            | This API sets the callback for async cloud to device method calls.
[IoTHubDeviceClient_DeviceMethodResponse](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-devicemethodresponse.md)            | This API responds to an asnyc method callback identified the methodId.
[IoTHubDeviceClient_UploadToBlobAsync](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-uploadtoblobasync.md)            | IoTHubDeviceClient_UploadToBlobAsync uploads data from memory to a file in Azure Blob Storage.
[IoTHubDeviceClient_UploadMultipleBlocksToBlobAsync](./iot-c-ref-iothub-device-client-h/iothubdeviceclient-uploadmultipleblockstoblobasync.md)            | Uploads a file to a Blob storage in chunks, fed through the callback function provided by the user.

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IOTHUB_DEVICE_CLIENT_INSTANCE_TYPE            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
IOTHUB_DEVICE_CLIENT_HANDLE            | 

## Function documentation

#### IoTHubDeviceClient_CreateFromConnectionString 
[IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) [IoTHubDeviceClient_CreateFromConnectionString](#iothub__device__client_8h_1a659e9bb5f8633d6565c966a1424b27b8)(const char * connectionString,[IOTHUB_CLIENT_TRANSPORT_PROVIDER](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)

#### IoTHubDeviceClient_Create 
[IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) [IoTHubDeviceClient_Create](#iothub__device__client_8h_1ace8d1bb4134aa07dc83ed771a5eb1fb7)(const [IOTHUB_CLIENT_CONFIG](#struct_i_o_t_h_u_b___c_l_i_e_n_t___c_o_n_f_i_g) * config)

#### IoTHubDeviceClient_CreateWithTransport 
[IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) [IoTHubDeviceClient_CreateWithTransport](#iothub__device__client_8h_1a20e32644525bd67493dab5c1f08975b4)([TRANSPORT_HANDLE](#iothub__transport__ll_8h_1a085a6035b065e4f48f3789e428235aa4) transportHandle,const [IOTHUB_CLIENT_CONFIG](#struct_i_o_t_h_u_b___c_l_i_e_n_t___c_o_n_f_i_g) * config)

#### IoTHubDeviceClient_CreateFromDeviceAuth 
[IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) [IoTHubDeviceClient_CreateFromDeviceAuth](#iothub__device__client_8h_1ad3fdf9efcd38a533a213f556b479ba56)(const char * iothub_uri,const char * device_id,[IOTHUB_CLIENT_TRANSPORT_PROVIDER](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)

#### IoTHubDeviceClient_Destroy 
void [IoTHubDeviceClient_Destroy](#iothub__device__client_8h_1a2991e03140462e9cc1606ccf25e8b412)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle)

#### IoTHubDeviceClient_SendEventAsync 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_SendEventAsync](#iothub__device__client_8h_1a85fdfe3dface6a158db18bac7e21e296)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,[IOTHUB_MESSAGE_HANDLE](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) eventMessageHandle,[IOTHUB_CLIENT_EVENT_CONFIRMATION_CALLBACK](#iothub__client__core__common_8h_1a41b17fcb2cb70587e3576226561648a0) eventConfirmationCallback,void * userContextCallback)

#### IoTHubDeviceClient_GetSendStatus 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_GetSendStatus](#iothub__device__client_8h_1a1b0ed9ddf82f4a32afc7df469452e0cc)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,[IOTHUB_CLIENT_STATUS](#iothub__client__core__common_8h_1af80b6370369f3c1bb53399deccb4491c) * iotHubClientStatus)

#### IoTHubDeviceClient_SetMessageCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_SetMessageCallback](#iothub__device__client_8h_1a530ac14eac99171cbf53a1b72992791f)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,[IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC](#iothub__client__core__common_8h_1adf7097e8fc9e34f26dd9347d4eaa5f8d) messageCallback,void * userContextCallback)

#### IoTHubDeviceClient_SetConnectionStatusCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_SetConnectionStatusCallback](#iothub__device__client_8h_1a905f59a848d7fbf0ae28f44ceff97e6c)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,[IOTHUB_CLIENT_CONNECTION_STATUS_CALLBACK](#iothub__client__core__common_8h_1ad0d7e0712e620b1d55e72652f4f4f560) connectionStatusCallback,void * userContextCallback)

#### IoTHubDeviceClient_SetRetryPolicy 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_SetRetryPolicy](#iothub__device__client_8h_1a53604d8d75556ded769b7947268beec8)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,[IOTHUB_CLIENT_RETRY_POLICY](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) retryPolicy,size_t retryTimeoutLimitInSeconds)

#### IoTHubDeviceClient_GetRetryPolicy 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_GetRetryPolicy](#iothub__device__client_8h_1a7e001ad2e02069d7b9773f8f245fae77)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,[IOTHUB_CLIENT_RETRY_POLICY](#iothub__client__core__common_8h_1a361221e523247855ff0a05c2e2870e4a) * retryPolicy,size_t * retryTimeoutLimitInSeconds)

#### IoTHubDeviceClient_GetLastMessageReceiveTime 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_GetLastMessageReceiveTime](#iothub__device__client_8h_1abc0085250813091a1e78fe4e07fa23ba)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,time_t * lastMessageReceiveTime)

#### IoTHubDeviceClient_SetOption 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_SetOption](#iothub__device__client_8h_1abde0ae9b104a57268e63e91e0dc2534f)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,const char * optionName,const void * value)

#### IoTHubDeviceClient_SetDeviceTwinCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_SetDeviceTwinCallback](#iothub__device__client_8h_1a614af0cf6dad5cc0544319587cb9e6d2)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,[IOTHUB_CLIENT_DEVICE_TWIN_CALLBACK](#iothub__client__core__common_8h_1a3020471f05025405840d9c43466122dc) deviceTwinCallback,void * userContextCallback)

#### IoTHubDeviceClient_SendReportedState 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_SendReportedState](#iothub__device__client_8h_1a8b0347cae8cb353e14d210fef0ab410e)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,const unsigned char * reportedState,size_t size,[IOTHUB_CLIENT_REPORTED_STATE_CALLBACK](#iothub__client__core__common_8h_1a9ae117da9222a5138e31a8953ce18bbc) reportedStateCallback,void * userContextCallback)

#### IoTHubDeviceClient_SetDeviceMethodCallback 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_SetDeviceMethodCallback](#iothub__device__client_8h_1ae63700fcfa5d57ed81d071965ad3afd9)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,[IOTHUB_CLIENT_DEVICE_METHOD_CALLBACK_ASYNC](#iothub__client__core__common_8h_1aa758c6c04994938fae9257289760d01a) deviceMethodCallback,void * userContextCallback)

#### IoTHubDeviceClient_DeviceMethodResponse 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_DeviceMethodResponse](#iothub__device__client_8h_1a0a0909124da66a5d0dcd5c172fe7eaea)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,[METHOD_HANDLE](#iothub__transport__ll_8h_1a1cc79695294f89e97fb945066a3b3d77) methodId,const unsigned char * response,size_t response_size,int statusCode)

#### IoTHubDeviceClient_UploadToBlobAsync 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_UploadToBlobAsync](#iothub__device__client_8h_1a3ec9c3d33886fd7814dab05e074512cd)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,const char * destinationFileName,const unsigned char * source,size_t size,[IOTHUB_CLIENT_FILE_UPLOAD_CALLBACK](#iothub__client__core__common_8h_1a039d574a949c85ba9c183c88d4ce03bf) iotHubClientFileUploadCallback,void * context)

#### IoTHubDeviceClient_UploadMultipleBlocksToBlobAsync 
[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_UploadMultipleBlocksToBlobAsync](#iothub__device__client_8h_1a973fec89efccbd3bb0af1c703a6adc79)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,const char * destinationFileName,[IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK_EX](#iothub__client__core__common_8h_1a0d9944dec4c4dd2bdd75cebb466dcf6c) getDataCallbackEx,void * context)

