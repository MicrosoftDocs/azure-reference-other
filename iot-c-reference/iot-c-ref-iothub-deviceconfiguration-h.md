# Header file iothub_deviceconfiguration.h 

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

## Function documentation

#### IOTHUB_DEVICE_CONFIGURATION_RESULTStrings 
const char * [IOTHUB_DEVICE_CONFIGURATION_RESULTStrings](#iothub__deviceconfiguration_8h_1a2e62a20a0e554dec0dbad03d134a3557)([IOTHUB_DEVICE_CONFIGURATION_RESULT](#iothub__deviceconfiguration_8h_1ac7d4e5e1c224c46fc993541e145b59d6) value)

#### IOTHUB_DEVICE_CONFIGURATION_RESULT_FromString 
int [IOTHUB_DEVICE_CONFIGURATION_RESULT_FromString](#iothub__deviceconfiguration_8h_1aba3aa92fc984660cb68188d2de97fa0b)(const char * enumAsString,[IOTHUB_DEVICE_CONFIGURATION_RESULT](#iothub__deviceconfiguration_8h_1ac7d4e5e1c224c46fc993541e145b59d6) * destination)

#### IOTHUB_DEVICECONFIGURATION_REQUEST_MODEStrings 
const char * [IOTHUB_DEVICECONFIGURATION_REQUEST_MODEStrings](#iothub__deviceconfiguration_8h_1adeca4ee7897cae7bd95818eeba2f883b)([IOTHUB_DEVICECONFIGURATION_REQUEST_MODE](#iothub__deviceconfiguration_8h_1a1c193edc742548a53c72c96406a35536) value)

#### IOTHUB_DEVICECONFIGURATION_REQUEST_MODE_FromString 
int [IOTHUB_DEVICECONFIGURATION_REQUEST_MODE_FromString](#iothub__deviceconfiguration_8h_1afce1096a6815c2e90c91d91cd5ff1bf2)(const char * enumAsString,[IOTHUB_DEVICECONFIGURATION_REQUEST_MODE](#iothub__deviceconfiguration_8h_1a1c193edc742548a53c72c96406a35536) * destination)

#### IoTHubDeviceConfiguration_Create 
[IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE](#iothub__deviceconfiguration_8h_1a6b6d0ee5e70f65ee692e420e50ef805c) [IoTHubDeviceConfiguration_Create](#iothub__deviceconfiguration_8h_1a8dd0eaaa96d7d9c87ab68bb5f78adff9)([IOTHUB_SERVICE_CLIENT_AUTH_HANDLE](#iothub__service__client__auth_8h_1a47d2f6357931c33108eb9fba95d8730b) serviceClientHandle)

#### IoTHubDeviceConfiguration_Destroy 
void [IoTHubDeviceConfiguration_Destroy](#iothub__deviceconfiguration_8h_1ad78bc705ac861944255ef3f7b4cd2197)([IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE](#iothub__deviceconfiguration_8h_1a6b6d0ee5e70f65ee692e420e50ef805c) serviceClientDeviceConfigurationHandle)

#### IoTHubDeviceConfiguration_GetConfigurations 
[IOTHUB_DEVICE_CONFIGURATION_RESULT](#iothub__deviceconfiguration_8h_1ac7d4e5e1c224c46fc993541e145b59d6) [IoTHubDeviceConfiguration_GetConfigurations](#iothub__deviceconfiguration_8h_1a76b5c792dd547475f8850a21cc0c95c1)([IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE](#iothub__deviceconfiguration_8h_1a6b6d0ee5e70f65ee692e420e50ef805c) serviceClientDeviceConfigurationHandle,size_t maxConfigurationsCount,[SINGLYLINKEDLIST_HANDLE](#singlylinkedlist_8h_1a355ba061e4132f7817d6d1963d33382a) configurationsList)

#### IoTHubDeviceConfiguration_GetConfiguration 
[IOTHUB_DEVICE_CONFIGURATION_RESULT](#iothub__deviceconfiguration_8h_1ac7d4e5e1c224c46fc993541e145b59d6) [IoTHubDeviceConfiguration_GetConfiguration](#iothub__deviceconfiguration_8h_1ae51909622d06cab524846b36c2424736)([IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE](#iothub__deviceconfiguration_8h_1a6b6d0ee5e70f65ee692e420e50ef805c) serviceClientDeviceConfigurationHandle,const char * configurationId,[IOTHUB_DEVICE_CONFIGURATION](#struct_i_o_t_h_u_b___d_e_v_i_c_e___c_o_n_f_i_g_u_r_a_t_i_o_n) * configuration)

#### IoTHubDeviceConfiguration_AddConfiguration 
[IOTHUB_DEVICE_CONFIGURATION_RESULT](#iothub__deviceconfiguration_8h_1ac7d4e5e1c224c46fc993541e145b59d6) [IoTHubDeviceConfiguration_AddConfiguration](#iothub__deviceconfiguration_8h_1a89aefeacbcb9da8bdc093a70da75c95c)([IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE](#iothub__deviceconfiguration_8h_1a6b6d0ee5e70f65ee692e420e50ef805c) serviceClientDeviceConfigurationHandle,const [IOTHUB_DEVICE_CONFIGURATION_ADD](#struct_i_o_t_h_u_b___d_e_v_i_c_e___c_o_n_f_i_g_u_r_a_t_i_o_n___a_d_d) * configurationAdd,[IOTHUB_DEVICE_CONFIGURATION](#struct_i_o_t_h_u_b___d_e_v_i_c_e___c_o_n_f_i_g_u_r_a_t_i_o_n) * configuration)

#### IoTHubDeviceConfiguration_UpdateConfiguration 
[IOTHUB_DEVICE_CONFIGURATION_RESULT](#iothub__deviceconfiguration_8h_1ac7d4e5e1c224c46fc993541e145b59d6) [IoTHubDeviceConfiguration_UpdateConfiguration](#iothub__deviceconfiguration_8h_1aa290751fb3af00021b7d4d851861a133)([IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE](#iothub__deviceconfiguration_8h_1a6b6d0ee5e70f65ee692e420e50ef805c) serviceClientDeviceConfigurationHandle,const [IOTHUB_DEVICE_CONFIGURATION](#struct_i_o_t_h_u_b___d_e_v_i_c_e___c_o_n_f_i_g_u_r_a_t_i_o_n) * configuration)

#### IoTHubDeviceConfiguration_DeleteConfiguration 
[IOTHUB_DEVICE_CONFIGURATION_RESULT](#iothub__deviceconfiguration_8h_1ac7d4e5e1c224c46fc993541e145b59d6) [IoTHubDeviceConfiguration_DeleteConfiguration](#iothub__deviceconfiguration_8h_1aff7e7d0bcdb39e99c434c4adbc0046be)([IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE](#iothub__deviceconfiguration_8h_1a6b6d0ee5e70f65ee692e420e50ef805c) serviceClientDeviceConfigurationHandle,const char * configurationId)

#### IoTHubDeviceConfiguration_ApplyConfigurationContentToDeviceOrModule 
[IOTHUB_DEVICE_CONFIGURATION_RESULT](#iothub__deviceconfiguration_8h_1ac7d4e5e1c224c46fc993541e145b59d6) [IoTHubDeviceConfiguration_ApplyConfigurationContentToDeviceOrModule](#iothub__deviceconfiguration_8h_1a85f9a43f356ef17d453a644d7927940a)([IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE](#iothub__deviceconfiguration_8h_1a6b6d0ee5e70f65ee692e420e50ef805c) serviceClientDeviceConfigurationHandle,const char * deviceOrModuleId,const [IOTHUB_DEVICE_CONFIGURATION_CONTENT](#struct_i_o_t_h_u_b___d_e_v_i_c_e___c_o_n_f_i_g_u_r_a_t_i_o_n___c_o_n_t_e_n_t) * configurationContent)

#### IoTHubDeviceConfiguration_FreeConfigurationMembers 
void [IoTHubDeviceConfiguration_FreeConfigurationMembers](#iothub__deviceconfiguration_8h_1af7d27d1b1c6451caa91a84d211679100)([IOTHUB_DEVICE_CONFIGURATION](#struct_i_o_t_h_u_b___d_e_v_i_c_e___c_o_n_f_i_g_u_r_a_t_i_o_n) * configuration)

