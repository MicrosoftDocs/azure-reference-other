# IoTHubDeviceClient_Create()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h](../iot-c-ref-iothub-device-client-h.md)"  

## Syntax

```C
IOTHUB_DEVICE_CLIENT_HANDLE IoTHubDeviceClient_Create(
  const   config
);
```

Creates a IoT Hub client for communication with an existing IoT Hub using the specified parameters.

## Parameters
* **:config** Pointer to an `[IOTHUB_CLIENT_CONFIG](#struct_i_o_t_h_u_b___c_l_i_e_n_t___c_o_n_f_i_g)` structure

The API does not allow sharing of a connection across multiple devices. This is a blocking call.

## Returns
A non-NULL `IOTHUB_DEVICE_CLIENT_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

