# IoTHubDeviceClient_CreateFromDeviceAuth()

Creates a IoT Hub client for communication with an existing IoT Hub using the device auth module.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h](../iot-c-ref-iothub-device-client-h.md)"  
```C
IOTHUB_DEVICE_CLIENT_HANDLE IoTHubDeviceClient_CreateFromDeviceAuth(
  const char *                      iothub_uri,
  const char *                      device_id,
  IOTHUB_CLIENT_TRANSPORT_PROVIDER  protocol
);
```

## Parameters
* `iothub_uri` Pointer to an ioThub hostname received in the registration process 

* `device_id` Pointer to the device Id of the device 

* `protocol` Function pointer for protocol implementation

## Return Value
A non-NULL IOTHUB_DEVICE_CLIENT_HANDLE value that is used when invoking other functions for IoT Hub client and NULL on failure.

