# IoTHubClient_LL_CreateFromConnectionString()

Creates a IoT Hub client for communication with an existing IoT Hub using the specified connection string parameter.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h](../iot-c-ref-iothub-client-ll-h.md)"  
```C
IOTHUB_CLIENT_LL_HANDLE IoTHubClient_LL_CreateFromConnectionString(
  const char *                      connectionString,
  IOTHUB_CLIENT_TRANSPORT_PROVIDER  protocol
);
```

## Parameters
* `connectionString` Pointer to a character string 

* `protocol` Function pointer for protocol implementation

Sample connection string: 
```
HostName=[IoT Hub name goes here].[IoT Hub suffix goes here, e.g., private.azure-devices-int.net];DeviceId=[Device ID goes here];SharedAccessKey=[Device key goes here];
```

## Return Value
A non-NULL `IOTHUB_CLIENT_LL_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

