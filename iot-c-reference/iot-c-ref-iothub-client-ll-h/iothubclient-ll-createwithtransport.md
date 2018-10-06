# IoTHubClient_LL_CreateWithTransport()

Creates a IoT Hub client for communication with an existing IoT Hub using an existing transport.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h](../iot-c-ref-iothub-client-ll-h.md)"  
```C
IOTHUB_CLIENT_LL_HANDLE IoTHubClient_LL_CreateWithTransport(
  const   config
);
```

## Parameters
* `config` Pointer to an `[IOTHUB_CLIENT_DEVICE_CONFIG](#undefined)` structure

The API *allows* sharing of a connection across multiple devices. This is a blocking call.

## Return Value
A non-NULL `IOTHUB_CLIENT_LL_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

