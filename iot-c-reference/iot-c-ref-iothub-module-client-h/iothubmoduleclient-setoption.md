# IoTHubModuleClient_SetOption()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h](../iot-c-ref-iothub-module-client-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_SetOption(
  IOTHUB_MODULE_CLIENT_HANDLE  iotHubModuleClientHandle,
  const char *                 optionName,
  const void *                 value);
```

This API sets a runtime option identified by parameter `optionName` to a value pointed to by `value`. `optionName` and the data type `value` is pointing to are specific for every option.

## Parameters
* `iotHubModuleClientHandle`The handle created by a call to the create function. 

* `optionName`Name of the option. 

* `value`The value.

The options that can be set via this API are:

* **timeout** - the maximum time in milliseconds a communication is allowed to use. `value` is a pointer to an `unsigned``int` with the timeout value in milliseconds. This is only supported for the HTTP protocol as of now. When the HTTP protocol uses CURL, the meaning of the parameter is *total request time*. When the HTTP protocol uses winhttp, the meaning is the same as the `dwSendTimeout` and `dwReceiveTimeout` parameters of the [WinHttpSetTimeouts](https://msdn.microsoft.com/en-us/library/windows/desktop/aa384116(v=vs.85).aspx) API.

* **CURLOPT_LOW_SPEED_LIMIT** - only available for HTTP protocol and only when CURL is used. It has the same meaning as CURL's option with the same name. `value` is pointer to a long.

* **CURLOPT_LOW_SPEED_TIME** - only available for HTTP protocol and only when CURL is used. It has the same meaning as CURL's option with the same name. `value` is pointer to a long.

* **CURLOPT_FORBID_REUSE** - only available for HTTP protocol and only when CURL is used. It has the same meaning as CURL's option with the same name. `value` is pointer to a long.

* **CURLOPT_FRESH_CONNECT** - only available for HTTP protocol and only when CURL is used. It has the same meaning as CURL's option with the same name. `value` is pointer to a long.

* **CURLOPT_VERBOSE** - only available for HTTP protocol and only when CURL is used. It has the same meaning as CURL's option with the same name. `value` is pointer to a long.

* **messageTimeout** - the maximum time in milliseconds until a message is timeouted. The time starts at IoTHubModuleClient_SendEventAsync. By default, messages do not expire. `is` a pointer to a uint64_t

* **svc2cl_keep_alive_timeout_secs** - the AMQP service side keep alive interval in seconds. After the connection established the client requests the server to set the keep alive interval for given time. If it is not set then the default 240 sec applies. If it is set to zero the server will not send keep alive messages to the client.

* **cl2svc_keep_alive_send_ratio** - the AMQP client side keep alive interval in seconds. After the connection established the server requests the client to set the keep alive interval for given time. If it is not set then the default ratio of 1/2 is applied. The ratio has to be greater than 0.0 and equal to or less than 0.9

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

