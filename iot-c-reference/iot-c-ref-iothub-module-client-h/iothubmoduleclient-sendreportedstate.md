# IoTHubModuleClient_SendReportedState()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h"](../iot-c-ref-iothub-module-client-h.md)  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_SendReportedState(
  IOTHUB_MODULE_CLIENT_HANDLE            	iotHubModuleClientHandle,
  const unsigned char *                  	reportedState,
  size_t                                 	size,
  IOTHUB_CLIENT_REPORTED_STATE_CALLBACK  	reportedStateCallback,
  void *                                 	userContextCallback
);

```

This API sends a report of the module's properties and their current values.

#### Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `reportedState` The current module property values to be 'reported' to the IoTHub. 

* `reportedStateCallback` The callback specified by the module client to be called with the result of the transaction. 

* `userContextCallback` User specified context that will be provided to the callback. This can be `NULL`.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubModuleClient_Destroy](#iothub__module__client_8h_1af70545d139f41f0bc8acb51725c2d0de) function from within any callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

