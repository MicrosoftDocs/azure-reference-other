# IoTHubDeviceClient_CreateWithTransport()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h"](../iot-c-ref-iothub-device-client-h.md)  

**[IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) [IoTHubDeviceClient_CreateWithTransport](#iothub__device__client_8h_1a20e32644525bd67493dab5c1f08975b4)([TRANSPORT_HANDLE](#iothub__transport__ll_8h_1a085a6035b065e4f48f3789e428235aa4) transportHandle,const [IOTHUB_CLIENT_CONFIG](#struct_i_o_t_h_u_b___c_l_i_e_n_t___c_o_n_f_i_g) * config)**

Creates a IoT Hub client for communication with an existing IoT Hub using the specified parameters.

#### Parameters
* `transportHandle` TRANSPORT_HANDLE which represents a connection. 

* `config` Pointer to an `[IOTHUB_CLIENT_CONFIG](#struct_i_o_t_h_u_b___c_l_i_e_n_t___c_o_n_f_i_g)` structure

The API allows sharing of a connection across multiple devices. This is a blocking call.

#### Returns
A non-NULL `IOTHUB_DEVICE_CLIENT_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

