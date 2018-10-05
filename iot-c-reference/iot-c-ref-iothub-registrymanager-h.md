# iothub_registrymanager.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "azure_c_shared_utility/crt_abstractions.h"  
\#include "[azure_c_shared_utility/singlylinkedlist.h](iot-c-ref-singlylinkedlist-h.md)"  
\#include "[azure_c_shared_utility/map.h](iot-c-ref-map-h.md)"  
\#include "[iothub_service_client_auth.h](iot-c-ref-iothub-service-client-auth-h.md)"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IOTHUB_REGISTRYMANAGER_RESULTStrings](./iot-c-ref-iothub-registrymanager-h/iothub-registrymanager-resultstrings.md)            | 
[IOTHUB_REGISTRYMANAGER_RESULT_FromString](./iot-c-ref-iothub-registrymanager-h/iothub-registrymanager-result-fromstring.md)            | 
[IOTHUB_REGISTRYMANAGER_AUTH_METHODStrings](./iot-c-ref-iothub-registrymanager-h/iothub-registrymanager-auth-methodstrings.md)            | 
[IOTHUB_REGISTRYMANAGER_AUTH_METHOD_FromString](./iot-c-ref-iothub-registrymanager-h/iothub-registrymanager-auth-method-fromstring.md)            | 
[IoTHubRegistryManager_FreeDeviceExMembers](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-freedeviceexmembers.md)            | Free members of the [IOTHUB_DEVICE_EX](#struct_i_o_t_h_u_b___d_e_v_i_c_e___e_x) structure (NOT the structure itself)
[IoTHubRegistryManager_FreeModuleMembers](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-freemodulemembers.md)            | Free members of the [IOTHUB_MODULE](#struct_i_o_t_h_u_b___m_o_d_u_l_e) structure (NOT the structure itself)
[IoTHubRegistryManager_Create](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-create.md)            | Creates a IoT Hub Registry Manager handle for use it in consequent APIs.
[IoTHubRegistryManager_Destroy](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-destroy.md)            | Disposes of resources allocated by the IoT Hub Registry Manager.
[IoTHubRegistryManager_CreateDevice_Ex](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-createdevice-ex.md)            | Creates a device on IoT Hub.
[IoTHubRegistryManager_GetDevice_Ex](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getdevice-ex.md)            | Gets device info for a given device.
[IoTHubRegistryManager_UpdateDevice_Ex](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-updatedevice-ex.md)            | Updates a device on IoT Hub.
[IoTHubRegistryManager_DeleteDevice](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-deletedevice.md)            | Deletes a given device.
[IoTHubRegistryManager_GetStatistics](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getstatistics.md)            | Gets the registry statistic info.
[IoTHubRegistryManager_CreateModule](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-createmodule.md)            | Creates a module on IoT Hub.
[IoTHubRegistryManager_GetModule](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getmodule.md)            | Gets module info for a given module.
[IoTHubRegistryManager_UpdateModule](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-updatemodule.md)            | Updates a module on IoT Hub.
[IoTHubRegistryManager_DeleteModule](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-deletemodule.md)            | Deletes a given module.
[IoTHubRegistryManager_GetModuleList](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getmodulelist.md)            | Gets a list of modules registered on the specified device.
[IoTHubRegistryManager_CreateDevice](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-createdevice.md)            | Creates a device on IoT Hub.
[IoTHubRegistryManager_GetDevice](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getdevice.md)            | Gets device info for a given device.
[IoTHubRegistryManager_UpdateDevice](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-updatedevice.md)            | Updates a device on IoT Hub.
[IoTHubRegistryManager_GetDeviceList](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getdevicelist.md)            | 

## Structures

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IOTHUB_DEVICE_EX](./iot-c-ref-iothub-registrymanager-h/iothub-device-ex.md)            | 
[IOTHUB_REGISTRY_DEVICE_CREATE_EX](./iot-c-ref-iothub-registrymanager-h/iothub-registry-device-create-ex.md)            | 
[IOTHUB_REGISTRY_DEVICE_UPDATE_EX](./iot-c-ref-iothub-registrymanager-h/iothub-registry-device-update-ex.md)            | 
[IOTHUB_REGISTRY_STATISTICS](./iot-c-ref-iothub-registrymanager-h/iothub-registry-statistics.md)            | 
[IOTHUB_MODULE](./iot-c-ref-iothub-registrymanager-h/iothub-module.md)            | 
[IOTHUB_REGISTRY_MODULE_CREATE](./iot-c-ref-iothub-registrymanager-h/iothub-registry-module-create.md)            | 
[IOTHUB_REGISTRY_MODULE_UPDATE](./iot-c-ref-iothub-registrymanager-h/iothub-registry-module-update.md)            | 
[IOTHUB_REGISTRYMANAGER](./iot-c-ref-iothub-registrymanager-h/iothub-registrymanager.md)            | Structure to store IoTHub authentication information.
[IOTHUB_DEVICE](./iot-c-ref-iothub-registrymanager-h/iothub-device.md)            | 
[IOTHUB_REGISTRY_DEVICE_CREATE](./iot-c-ref-iothub-registrymanager-h/iothub-registry-device-create.md)            | 
[IOTHUB_REGISTRY_DEVICE_UPDATE](./iot-c-ref-iothub-registrymanager-h/iothub-registry-device-update.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IOTHUB_REGISTRYMANAGER_RESULT_VALUES            | 
IOTHUB_REGISTRYMANAGER_AUTH_METHOD_VALUES            | 
IOTHUB_DEVICE_EX_VERSION_1            | 
IOTHUB_REGISTRY_DEVICE_CREATE_EX_VERSION_1            | 
IOTHUB_REGISTRY_DEVICE_UPDATE_EX_VERSION_1            | 
IOTHUB_MODULE_VERSION_1            | 
IOTHUB_REGISTRY_MODULE_CREATE_VERSION_1            | 
IOTHUB_REGISTRY_MODULE_UPDATE_VERSION_1            | 

## Typedefs

####IOTHUB_REGISTRYMANAGER_HANDLE
typedef struct IOTHUB_REGISTRYMANAGER_TAG * IOTHUB_REGISTRYMANAGER_HANDLE()

Handle to hide struct and use it in consequent APIs.

