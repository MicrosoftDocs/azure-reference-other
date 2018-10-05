# IoTHubRegistryManager_UpdateDevice()

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  

## Syntax

```C
IOTHUB_REGISTRYMANAGER_RESULT IoTHubRegistryManager_UpdateDevice(
  IOTHUB_REGISTRYMANAGER_HANDLE  registryManagerHandle,

  IOTHUB_REGISTRY_DEVICE_UPDATE  deviceUpdate
);
```

Updates a device on IoT Hub.

DEPRECATED:: Use IoTHubRegistryManager_UpdateDevice_Ex instead 
## Parameters
* **:registryManagerHandle** The handle created by a call to the create function. 

* **:deviceUpdate** [IOTHUB_REGISTRY_DEVICE_UPDATE](#struct_i_o_t_h_u_b___r_e_g_i_s_t_r_y___d_e_v_i_c_e___u_p_d_a_t_e) structure containing the new device Id, primaryKey (optional), secondaryKey (optional), authentication method, and status

## Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

