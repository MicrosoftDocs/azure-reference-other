# IoTHubModuleClient_LL_SetModuleTwinCallback()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h"](../iot-c-ref-iothub-module-client-ll-h.md)  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_LL_SetModuleTwinCallback(
  IOTHUB_MODULE_CLIENT_LL_HANDLE      iotHubModuleClientHandle,
  IOTHUB_CLIENT_DEVICE_TWIN_CALLBACK  moduleTwinCallback,
  void *                              userContextCallback
);

```

This API specifies a call back to be used when the module receives a desired state update.

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `moduleTwinCallback` The callback specified by the module client to be used for updating the desired state. The callback will be called in response to patch request send by the IoTHub services. The payload will be passed to the callback, along with two version numbers:

* Desired:

* LastSeenReported: 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubModuleClient_LL_Destroy](#iothub__module__client__ll_8h_1aad2dd6c3c24f89a9cfa861754a845138) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

