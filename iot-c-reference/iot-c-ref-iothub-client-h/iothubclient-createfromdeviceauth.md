# IoTHubClient_CreateFromDeviceAuth()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client.h](../iot-c-ref-iothub-client-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_HANDLE IoTHubClient_CreateFromDeviceAuth(
  const char *                      iothub_uri,
  const char *                      device_id,
  IOTHUB_CLIENT_TRANSPORT_PROVIDER  protocol);
```

Creates a IoT Hub client for communication with an existing IoT Hub using the device auth module.

## Parameters
* `iothub_uri`Pointer to an ioThub hostname received in the registration process 

* `device_id`Pointer to the device Id of the device 

* `protocol`Function pointer for protocol implementation

## Returns
A non-NULL `IOTHUB_CLIENT_LL_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

