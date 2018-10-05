# iothub_client.h 

Extends the IoTHubCLient_LL module with additional features.

## Includes

\#include <stddef.h>  
\#include <stdint.h>  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "[iothub_transport_ll.h](iot-c-ref-iothub-transport-ll-h.md)"  
\#include "[iothub_client_core_ll.h](iot-c-ref-iothub-client-core-ll-h.md)"  
\#include "[iothub_client_core.h](iot-c-ref-iothub-client-core-h.md)"  
\#include "[iothub_client_ll.h](iot-c-ref-iothub-client-ll-h.md)"  

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

####IOTHUB_CLIENT_HANDLE

```C
typedef undefined IOTHUB_CLIENT_HANDLE()

```

