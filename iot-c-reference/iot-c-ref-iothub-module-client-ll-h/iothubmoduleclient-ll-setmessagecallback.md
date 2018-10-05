# IoTHubModuleClient_LL_SetMessageCallback()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h](../iot-c-ref-iothub-module-client-ll-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_LL_SetMessageCallback(
  IOTHUB_MODULE_CLIENT_LL_HANDLE        iotHubModuleClientHandle,
  IOTHUB_CLIENT_MESSAGE_CALLBACK_ASYNC  messageCallback,
  void *                                userContextCallback
);
```

Sets up the message callback to be invoked when Edge issues a message to the module. This is a blocking call.

## Parameters
* `iotHubModuleClientHandle`The handle created by a call to the create function. 

* `messageCallback`The callback specified by the module for receiving messages from IoT Hub. 

* `userContextCallback`User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubModuleClient_LL_Destroy](#iothub__module__client__ll_8h_1aad2dd6c3c24f89a9cfa861754a845138) function from within any callback.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

