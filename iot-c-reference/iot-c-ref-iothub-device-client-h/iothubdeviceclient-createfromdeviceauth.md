# IoTHubDeviceClient_CreateFromDeviceAuth()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h"](../iot-c-ref-iothub-device-client-h.md)  

**[IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) [IoTHubDeviceClient_CreateFromDeviceAuth](#iothub__device__client_8h_1ad3fdf9efcd38a533a213f556b479ba56)(const char * iothub_uri,const char * device_id,[IOTHUB_CLIENT_TRANSPORT_PROVIDER](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)**

Creates a IoT Hub client for communication with an existing IoT Hub using the device auth module.

#### Parameters
* `iothub_uri` Pointer to an ioThub hostname received in the registration process 

* `device_id` Pointer to the device Id of the device 

* `protocol` Function pointer for protocol implementation

#### Returns
A non-NULL `IOTHUB_DEVICE_CLIENT_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

