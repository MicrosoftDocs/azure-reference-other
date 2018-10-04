# IoTHubClient_LL_CreateFromConnectionString()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h"](../iot-c-ref-iothub-client-ll-h.md)  

**[IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) [IoTHubClient_LL_CreateFromConnectionString](#iothub__client__ll_8h_1aadecae0b07958725e83cae943250469d)(const char * connectionString,[IOTHUB_CLIENT_TRANSPORT_PROVIDER](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)**

Creates a IoT Hub client for communication with an existing IoT Hub using the specified connection string parameter.

#### Parameters
* `connectionString` Pointer to a character string 

* `protocol` Function pointer for protocol implementation

Sample connection string: 
```
HostName=[IoT Hub name goes here].[IoT Hub suffix goes here, e.g., private.azure-devices-int.net];DeviceId=[Device ID goes here];SharedAccessKey=[Device key goes here];

```

#### Returns
A non-NULL `IOTHUB_CLIENT_LL_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

