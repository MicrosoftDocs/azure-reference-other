# iothub_client_ll.h 

APIs that allow a user (usually a device) to communicate with an Azure IoTHub.

## Includes

\#include <stddef.h>  
\#include <stdint.h>  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "[iothub_transport_ll.h](iot-c-ref-iothub-transport-ll-h.md)"  
\#include "[iothub_client_core_ll.h](iot-c-ref-iothub-client-core-ll-h.md)"  

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

## Type definitions

#### IOTHUB_CLIENT_LL_HANDLE

```C
typedef struct IOTHUB_CLIENT_CORE_LL_HANDLE_DATA_TAG* IOTHUB_CLIENT_LL_HANDLE;
```

