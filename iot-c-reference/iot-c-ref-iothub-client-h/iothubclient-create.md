# IoTHubClient_Create()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client.h"](../iot-c-ref-iothub-client-h.md)  

[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) `[`IoTHubClient_Create`](#iothub__client_8h_1a7e4253f4df8cdef79cbe44d33c73547d)(const `[`IOTHUB_CLIENT_CONFIG`](#struct_i_o_t_h_u_b___c_l_i_e_n_t___c_o_n_f_i_g) * config)`

Creates a IoT Hub client for communication with an existing IoT Hub using the specified parameters.

#### Parameters
* `config` Pointer to an `[IOTHUB_CLIENT_CONFIG](#struct_i_o_t_h_u_b___c_l_i_e_n_t___c_o_n_f_i_g)` structure

The API does not allow sharing of a connection across multiple devices. This is a blocking call.

#### Returns
A non-NULL `IOTHUB_CLIENT_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

