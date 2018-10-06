# IoTHubModuleClient_GetRetryPolicy()

Sets up the connection status callback to be invoked representing the status of the connection to IOT Hub. This is a blocking call.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h](../iot-c-ref-iothub-module-client-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_GetRetryPolicy(
  IOTHUB_MODULE_CLIENT_HANDLE  iotHubModuleClientHandle,
  IOTHUB_CLIENT_RETRY_POLICY   retryPolicy,
  size_t *                     retryTimeoutLimitInSeconds
);
```

## Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `retryPolicy` Out parameter containing the policy to use to reconnect to IoT Hub. 

* `retryTimeoutLimitInSeconds` Out parameter containing maximum amount of time in seconds to attempt reconnection to IOT Hub.

**NOTE:** The application behavior is undefined if the user calls the [IoTHubModuleClient_LL_Destroy](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    }) function from within any callback.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

