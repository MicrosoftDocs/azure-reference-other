# IoTHubDeviceClient_LL_CreateFromConnectionString()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h](../iot-c-ref-iothub-device-client-ll-h.md)"  

## Syntax

```C
IOTHUB_DEVICE_CLIENT_LL_HANDLE IoTHubDeviceClient_LL_CreateFromConnectionString(
  const char *                      connectionString,
  IOTHUB_CLIENT_TRANSPORT_PROVIDER  protocol
);
```

Creates a IoT Hub client for communication with an existing IoT Hub using the specified connection string parameter.

## Parameters
* `connectionString`Pointer to a character string 

* `protocol`Function pointer for protocol implementation

Sample connection string: 
```
HostName=[IoT Hub name goes here].[IoT Hub suffix goes here, e.g., private.azure-devices-int.net];DeviceId=[Device ID goes here];SharedAccessKey=[Device key goes here];

```

## Returns
A non-NULL `IOTHUB_DEVICE_CLIENT_LL_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

