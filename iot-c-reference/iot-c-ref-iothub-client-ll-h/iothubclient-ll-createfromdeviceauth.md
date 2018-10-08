# IoTHubClient_LL_CreateFromDeviceAuth()

Creates a IoT Hub client for communication with an existing IoT Hub using the device auth module.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h](../iot-c-ref-iothub-client-ll-h.md)"  
```C
IOTHUB_CLIENT_LL_HANDLE IoTHubClient_LL_CreateFromDeviceAuth(
  const char *                      iothub_uri,
  const char *                      device_id,
  IOTHUB_CLIENT_TRANSPORT_PROVIDER  protocol
);
```

## Parameters
* `iothub_uri` Pointer to an ioThub hostname received in the registration process 

* `device_id` Pointer to the device Id of the device 

* `device_auth_handle` a device auth handle used to generate the connection string 

* `protocol` Function pointer for protocol implementation

## Return Value
A non-NULL IOTHUB_CLIENT_LL_HANDLE value that is used when invoking other functions for IoT Hub client and NULL on failure.

