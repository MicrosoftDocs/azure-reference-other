# IoTHubModuleClient_LL_SetConnectionStatusCallback()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h](../iot-c-ref-iothub-module-client-ll-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_LL_SetConnectionStatusCallback(
  IOTHUB_MODULE_CLIENT_LL_HANDLE            iotHubModuleClientHandle,
  IOTHUB_CLIENT_CONNECTION_STATUS_CALLBACK  connectionStatusCallback,
  void *                                    userContextCallback);
```

Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.

## Parameters
* `iotHubModuleClientHandle`The handle created by a call to the create function. 

* `connectionStatusCallback`The callback specified by the module for receiving updates about the status of the connection to IoT Hub. 

* `userContextCallback`User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubModuleClient_LL_Destroy](#iothub__module__client__ll_8h_1aad2dd6c3c24f89a9cfa861754a845138) function from within any callback.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

