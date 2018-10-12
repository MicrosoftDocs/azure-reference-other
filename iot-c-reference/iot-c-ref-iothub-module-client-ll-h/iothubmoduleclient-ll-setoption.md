# IoTHubModuleClient_LL_SetOption()

This API sets a runtime option identified by parameter optionName to a value pointed to by value. optionName and the data type value is pointing to are specific for every option.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h](../iot-c-ref-iothub-module-client-ll-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubModuleClient_LL_SetOption(
  IOTHUB_MODULE_CLIENT_LL_HANDLE  iotHubModuleClientHandle,
  const char *                    optionName,
  const void *                    value
);
```

## Parameters
* `iotHubModuleClientHandle` The handle created by a call to the create function. 

* `optionName` Name of the option. 

* `value` The value.

The options that can be set via this API are:

* **timeout** - the maximum time in milliseconds a communication is allowed to use. value is a pointer to an unsignedint with the timeout value in milliseconds. This is only supported for the HTTP protocol as of now. When the HTTP protocol uses CURL, the meaning of the parameter is *total request time*. When the HTTP protocol uses winhttp, the meaning is the same as the dwSendTimeout and dwReceiveTimeout parameters of the [WinHttpSetTimeouts](https://msdn.microsoft.com/en-us/library/windows/desktop/aa384116(v=vs.85).aspx) API.

* **CURLOPT_LOW_SPEED_LIMIT** - only available for HTTP protocol and only when CURL is used. It has the same meaning as CURL's option with the same name. value is pointer to a long.

* **CURLOPT_LOW_SPEED_TIME** - only available for HTTP protocol and only when CURL is used. It has the same meaning as CURL's option with the same name. value is pointer to a long.

* **CURLOPT_FORBID_REUSE** - only available for HTTP protocol and only when CURL is used. It has the same meaning as CURL's option with the same name. value is pointer to a long.

* **CURLOPT_FRESH_CONNECT** - only available for HTTP protocol and only when CURL is used. It has the same meaning as CURL's option with the same name. value is pointer to a long.

* **CURLOPT_VERBOSE** - only available for HTTP protocol and only when CURL is used. It has the same meaning as CURL's option with the same name. value is pointer to a long.

* **keepalive** - available for MQTT protocol. Integer value that sets the interval in seconds when pings are sent to the server.

* **logtrace** - available for MQTT protocol. Boolean value that turns on and off the diagnostic logging.

* **sas_token_lifetime** - available for MQTT & AMQP protocol. size_t value that that determines the sas token timeout length.

## Return Value
IOTHUB_CLIENT_OK upon success or an error code upon failure.

