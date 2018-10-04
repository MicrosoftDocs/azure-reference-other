# IoTHubClient_CreateWithTransport()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client.h"](../iot-c-ref-iothub-client-h.md)  

## Syntax

```C
IOTHUB_CLIENT_HANDLE IoTHubClient_CreateWithTransport(
  TRANSPORT_HANDLE  transportHandle,
  const             config
);

```

Creates a IoT Hub client for communication with an existing IoT Hub using the specified parameters.

#### Parameters
* `transportHandle` TRANSPORT_HANDLE which represents a connection. 

* `config` Pointer to an `[IOTHUB_CLIENT_CONFIG](#struct_i_o_t_h_u_b___c_l_i_e_n_t___c_o_n_f_i_g)` structure

The API allows sharing of a connection across multiple devices. This is a blocking call.

#### Returns
A non-NULL `IOTHUB_CLIENT_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

