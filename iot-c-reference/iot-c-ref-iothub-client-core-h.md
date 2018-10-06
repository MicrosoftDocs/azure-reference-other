# iothub_client_core.h 

Extends the IoTHubClientCore_LL module with additional features.

## Includes

\#include <stddef.h>  
\#include <stdint.h>  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "[iothub_client_core_ll.h](iot-c-ref-iothub-client-core-ll-h.md)"  

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

## Macro definitions

#### IOTHUB_CLIENT_CORE_INSTANCE_TYPE

```C
#define IOTHUB_CLIENT_CORE_INSTANCE_TYPE
```

## Typedef documentation

#### IOTHUB_CLIENT_CORE_HANDLE

```C
typedef struct IOTHUB_CLIENT_CORE_INSTANCE_TAG* IOTHUB_CLIENT_CORE_HANDLE;
```

