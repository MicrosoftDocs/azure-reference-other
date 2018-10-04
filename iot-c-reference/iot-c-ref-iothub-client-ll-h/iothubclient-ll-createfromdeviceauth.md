# IoTHubClient_LL_CreateFromDeviceAuth()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h"](../iot-c-ref-iothub-client-ll-h.md)  

[`IOTHUB_CLIENT_LL_HANDLE`](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) `[`IoTHubClient_LL_CreateFromDeviceAuth`](#iothub__client__ll_8h_1aeccf0188b7a31fa475383eb44328f6d9)(const char * iothub_uri,const char * device_id,`[`IOTHUB_CLIENT_TRANSPORT_PROVIDER`](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)`

Creates a IoT Hub client for communication with an existing IoT Hub using the device auth module.

#### Parameters
* `iothub_uri` Pointer to an ioThub hostname received in the registration process 

* `device_id` Pointer to the device Id of the device 

* `device_auth_handle` a device auth handle used to generate the connection string 

* `protocol` Function pointer for protocol implementation

#### Returns
A non-NULL `IOTHUB_CLIENT_LL_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

