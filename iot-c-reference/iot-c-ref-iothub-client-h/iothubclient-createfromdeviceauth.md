# IoTHubClient_CreateFromDeviceAuth()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client.h"](../iot-c-ref-iothub-client-h.md)  

[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) `[`IoTHubClient_CreateFromDeviceAuth`](#iothub__client_8h_1ac10dff7a369ef9c39babca7ce4a69476)(const char * iothub_uri,const char * device_id,`[`IOTHUB_CLIENT_TRANSPORT_PROVIDER`](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)`

Creates a IoT Hub client for communication with an existing IoT Hub using the device auth module.

#### Parameters
* `iothub_uri` Pointer to an ioThub hostname received in the registration process 

* `device_id` Pointer to the device Id of the device 

* `protocol` Function pointer for protocol implementation

#### Returns
A non-NULL `IOTHUB_CLIENT_LL_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

