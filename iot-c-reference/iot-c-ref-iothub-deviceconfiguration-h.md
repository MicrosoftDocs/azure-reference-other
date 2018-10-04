# iothub_deviceconfiguration.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/crt_abstractions.h"  
\#include ["azure_c_shared_utility/singlylinkedlist.h"](iot-c-ref-singlylinkedlist-h.md)  
\#include <time.h>  
\#include ["iothub_service_client_auth.h"](iot-c-ref-iothub-service-client-auth-h.md)  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IOTHUB_DEVICE_CONFIGURATION_RESULTStrings](./iot-c-ref-iothub-deviceconfiguration-h/iothub-device-configuration-resultstrings.md)            | 
[IOTHUB_DEVICE_CONFIGURATION_RESULT_FromString](./iot-c-ref-iothub-deviceconfiguration-h/iothub-device-configuration-result-fromstring.md)            | 
[IOTHUB_DEVICECONFIGURATION_REQUEST_MODEStrings](./iot-c-ref-iothub-deviceconfiguration-h/iothub-deviceconfiguration-request-modestrings.md)            | 
[IOTHUB_DEVICECONFIGURATION_REQUEST_MODE_FromString](./iot-c-ref-iothub-deviceconfiguration-h/iothub-deviceconfiguration-request-mode-fromstring.md)            | 
[IoTHubDeviceConfiguration_Create](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-create.md)            | Creates a IoT Hub Service Client DeviceConfiguration handle for use it in consequent APIs.
[IoTHubDeviceConfiguration_Destroy](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-destroy.md)            | Disposes of resources allocated by the IoT Hub IoTHubDeviceConfiguration_Create.
[IoTHubDeviceConfiguration_GetConfigurations](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-getconfigurations.md)            | Retrieves the Configuration info for multiple configurations from IoT Hub.
[IoTHubDeviceConfiguration_GetConfiguration](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-getconfiguration.md)            | Retrieves the Configuration info for specified configurationId from IoT Hub.
[IoTHubDeviceConfiguration_AddConfiguration](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-addconfiguration.md)            | Adds the Configuration info to IoT Hub.
[IoTHubDeviceConfiguration_UpdateConfiguration](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-updateconfiguration.md)            | Updates the given Configuration in IoT Hub.
[IoTHubDeviceConfiguration_DeleteConfiguration](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-deleteconfiguration.md)            | Deletes the given Configuration from IoT Hub.
[IoTHubDeviceConfiguration_ApplyConfigurationContentToDeviceOrModule](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-applyconfigurationcontenttodeviceormodule.md)            | Deletes the given Configuration from IoT Hub.
[IoTHubDeviceConfiguration_FreeConfigurationMembers](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-freeconfigurationmembers.md)            | Free members of the [IOTHUB_DEVICE_CONFIGURATION](#struct_i_o_t_h_u_b___d_e_v_i_c_e___c_o_n_f_i_g_u_r_a_t_i_o_n) structure (NOT the structure itself)

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IOTHUB_DEVICE_CONFIGURATION_RESULT_VALUES            | 
IOTHUB_DEVICECONFIGURATION_REQUEST_MODE_VALUES            | 
IOTHUB_DEVICE_CONFIGURATION_SCHEMA_VERSION_1            | 
IOTHUB_DEVICE_CONFIGURATION_VERSION_1            | 
IOTHUB_DEVICE_CONFIGURATION_ADD_VERSION_1            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE            | Handle to hide struct and use it in consequent APIs.

