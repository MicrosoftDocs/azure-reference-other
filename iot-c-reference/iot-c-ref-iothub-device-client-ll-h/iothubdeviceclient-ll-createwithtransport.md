# IoTHubDeviceClient_LL_CreateWithTransport()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h"](../iot-c-ref-iothub-device-client-ll-h.md)  

[`IOTHUB_DEVICE_CLIENT_LL_HANDLE`](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) `[`IoTHubDeviceClient_LL_CreateWithTransport`](#iothub__device__client__ll_8h_1a044b4357c6a5450de02cf9c774dca87b)(const `[`IOTHUB_CLIENT_DEVICE_CONFIG`](#struct_i_o_t_h_u_b___c_l_i_e_n_t___d_e_v_i_c_e___c_o_n_f_i_g) * config)`

Creates a IoT Hub client for communication with an existing IoT Hub using an existing transport.

#### Parameters
* `config` Pointer to an `[IOTHUB_CLIENT_DEVICE_CONFIG](#struct_i_o_t_h_u_b___c_l_i_e_n_t___d_e_v_i_c_e___c_o_n_f_i_g)` structure

The API *allows* sharing of a connection across multiple devices. This is a blocking call.

#### Returns
A non-NULL `IOTHUB_DEVICE_CLIENT_LL_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

