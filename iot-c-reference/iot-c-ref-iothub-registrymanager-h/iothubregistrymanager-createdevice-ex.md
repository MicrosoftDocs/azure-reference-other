# IoTHubRegistryManager_CreateDevice_Ex()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h"](../iot-c-ref-iothub-registrymanager-h.md)  

## Syntax

```C
IOTHUB_REGISTRYMANAGER_RESULT IoTHubRegistryManager_CreateDevice_Ex(
  IOTHUB_REGISTRYMANAGER_HANDLE  	registryManagerHandle,
  const                          	deviceCreate,
  IOTHUB_DEVICE_EX               	device
);

```

Creates a device on IoT Hub.

#### Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `deviceCreate` [IOTHUB_REGISTRY_DEVICE_CREATE_EX](#struct_i_o_t_h_u_b___r_e_g_i_s_t_r_y___d_e_v_i_c_e___c_r_e_a_t_e___e_x) structure containing the new device Id, primaryKey (optional) and secondaryKey (optional) 

* `device` Input parameter, if it is not NULL will contain the created device info structure

#### Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

