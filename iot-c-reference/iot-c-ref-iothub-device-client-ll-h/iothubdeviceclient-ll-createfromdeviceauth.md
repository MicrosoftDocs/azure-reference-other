# IoTHubDeviceClient_LL_CreateFromDeviceAuth()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h"](../iot-c-ref-iothub-device-client-ll-h.md)  

**[IOTHUB_DEVICE_CLIENT_LL_HANDLE](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) [IoTHubDeviceClient_LL_CreateFromDeviceAuth](#iothub__device__client__ll_8h_1a0e84dff5ca26d7a915dcc61963db361e)(const char * iothub_uri,const char * device_id,[IOTHUB_CLIENT_TRANSPORT_PROVIDER](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)**

Creates a IoT Hub client for communication with an existing IoT Hub using the device auth module.

#### Parameters
* `iothub_uri` Pointer to an ioThub hostname received in the registration process 

* `device_id` Pointer to the device Id of the device 

* `device_auth_handle` A device auth handle used to generate the connection string 

* `protocol` Function pointer for protocol implementation

#### Returns
A non-NULL `IOTHUB_DEVICE_CLIENT_LL_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

