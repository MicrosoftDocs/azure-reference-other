# IoTHubClient_LL_Create()

Creates a IoT Hub client for communication with an existing IoT Hub using the specified parameters.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h](../iot-c-ref-iothub-client-ll-h.md)"  
```C
IOTHUB_CLIENT_LL_HANDLE IoTHubClient_LL_Create(
  const   config
);
```

## Parameters
* `config` Pointer to an [IOTHUB_CLIENT_CONFIG](#undefined) structure

The API does not allow sharing of a connection across multiple devices. This is a blocking call.

## Return Value
A non-NULL IOTHUB_CLIENT_LL_HANDLE value that is used when invoking other functions for IoT Hub client and NULL on failure.

