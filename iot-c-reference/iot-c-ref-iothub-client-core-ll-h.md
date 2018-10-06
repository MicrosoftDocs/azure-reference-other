# iothub_client_core_ll.h 

APIs that allow a user (usually a device) to communicate with an Azure IoTHub.

## Includes

\#include <time.h>  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "[iothub_transport_ll.h](iot-c-ref-iothub-transport-ll-h.md)"  
\#include "[iothub_client_core_common.h](iot-c-ref-iothub-client-core-common-h.md)"  

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

