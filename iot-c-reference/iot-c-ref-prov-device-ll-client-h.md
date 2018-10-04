# Header file prov_device_ll_client.h 

Stub comment for brief. Please update this comment.

## Includes

\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_prov_client/prov_transport.h"](iot-c-ref-prov-transport-h.md)  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[PROV_DEVICE_RESULTStrings](./iot-c-ref-prov-device-ll-client-h/prov-device-resultstrings.md)            | 
[PROV_DEVICE_RESULT_FromString](./iot-c-ref-prov-device-ll-client-h/prov-device-result-fromstring.md)            | 
[PROV_DEVICE_REG_STATUSStrings](./iot-c-ref-prov-device-ll-client-h/prov-device-reg-statusstrings.md)            | 
[PROV_DEVICE_REG_STATUS_FromString](./iot-c-ref-prov-device-ll-client-h/prov-device-reg-status-fromstring.md)            | 
[Prov_Device_LL_Create](./iot-c-ref-prov-device-ll-client-h/prov-device-ll-create.md)            | Creates a Provisioning Client for communications with the Device Provisioning Client Service.
[Prov_Device_LL_Destroy](./iot-c-ref-prov-device-ll-client-h/prov-device-ll-destroy.md)            | Disposes of resources allocated by the provisioning Client.
[Prov_Device_LL_Register_Device](./iot-c-ref-prov-device-ll-client-h/prov-device-ll-register-device.md)            | Asynchronous call initiates the registration of a device.
[Prov_Device_LL_DoWork](./iot-c-ref-prov-device-ll-client-h/prov-device-ll-dowork.md)            | Api to be called by user when work (registering device) can be done.
[Prov_Device_LL_SetOption](./iot-c-ref-prov-device-ll-client-h/prov-device-ll-setoption.md)            | API sets a runtime option identified by parameter optionName to a value pointed to by value.
[Prov_Device_LL_GetVersionString](./iot-c-ref-prov-device-ll-client-h/prov-device-ll-getversionstring.md)            | API to get the version of the provisioning client.

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
PROV_DEVICE_RESULT_VALUE            | 
PROV_DEVICE_REG_STATUS_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
PROV_DEVICE_LL_HANDLE            | 
PROV_DEVICE_CLIENT_REGISTER_DEVICE_CALLBACK            | 
PROV_DEVICE_CLIENT_REGISTER_STATUS_CALLBACK            | 
PROV_DEVICE_TRANSPORT_PROVIDER_FUNCTION            | 

## Function documentation

#### PROV_DEVICE_RESULTStrings 
const char * [PROV_DEVICE_RESULTStrings](#prov__device__ll__client_8h_1a9ab8328f20d8550cfe29b02bd23eec15)([PROV_DEVICE_RESULT](#prov__device__ll__client_8h_1a4e21aaa494a7ff52958e337551fde7eb) value)

#### PROV_DEVICE_RESULT_FromString 
int [PROV_DEVICE_RESULT_FromString](#prov__device__ll__client_8h_1a444af30ad058a0998ba3af63fbd150c0)(const char * enumAsString,[PROV_DEVICE_RESULT](#prov__device__ll__client_8h_1a4e21aaa494a7ff52958e337551fde7eb) * destination)

#### PROV_DEVICE_REG_STATUSStrings 
const char * [PROV_DEVICE_REG_STATUSStrings](#prov__device__ll__client_8h_1a98716d7d069ec68b350a972c96e1b5ab)([PROV_DEVICE_REG_STATUS](#prov__device__ll__client_8h_1aa49854aa442e8d497377076d841a7f72) value)

#### PROV_DEVICE_REG_STATUS_FromString 
int [PROV_DEVICE_REG_STATUS_FromString](#prov__device__ll__client_8h_1a1c6cdc180f1e221e27f14ddc7a52c371)(const char * enumAsString,[PROV_DEVICE_REG_STATUS](#prov__device__ll__client_8h_1aa49854aa442e8d497377076d841a7f72) * destination)

#### Prov_Device_LL_Create 
[PROV_DEVICE_LL_HANDLE](#prov__device__ll__client_8h_1aa6ce77119fc5a0c50d57a97a990cb54f) [Prov_Device_LL_Create](#prov__device__ll__client_8h_1a9f209da792720540561a27a5f82d62b2)(const char * uri,const char * scope_id,[PROV_DEVICE_TRANSPORT_PROVIDER_FUNCTION](#prov__device__ll__client_8h_1a6464d6b187cc71ac6e81938338d31d48) protocol)

#### Prov_Device_LL_Destroy 
void [Prov_Device_LL_Destroy](#prov__device__ll__client_8h_1a3634dea8a59ee510065e457a93e5c073)([PROV_DEVICE_LL_HANDLE](#prov__device__ll__client_8h_1aa6ce77119fc5a0c50d57a97a990cb54f) handle)

#### Prov_Device_LL_Register_Device 
[PROV_DEVICE_RESULT](#prov__device__ll__client_8h_1a4e21aaa494a7ff52958e337551fde7eb) [Prov_Device_LL_Register_Device](#prov__device__ll__client_8h_1ad466d9cb0750eefc15bafe006018ae6c)([PROV_DEVICE_LL_HANDLE](#prov__device__ll__client_8h_1aa6ce77119fc5a0c50d57a97a990cb54f) handle,[PROV_DEVICE_CLIENT_REGISTER_DEVICE_CALLBACK](#prov__device__ll__client_8h_1ac1a30031c36b065d7557ab76e919201f) register_callback,void * user_context,[PROV_DEVICE_CLIENT_REGISTER_STATUS_CALLBACK](#prov__device__ll__client_8h_1a992c5a15ab87f820c87ca2121cb1fd14) reg_status_cb,void * status_user_ctext)

#### Prov_Device_LL_DoWork 
void [Prov_Device_LL_DoWork](#prov__device__ll__client_8h_1a32587f168929aee7108416ebbee082d3)([PROV_DEVICE_LL_HANDLE](#prov__device__ll__client_8h_1aa6ce77119fc5a0c50d57a97a990cb54f) handle)

#### Prov_Device_LL_SetOption 
[PROV_DEVICE_RESULT](#prov__device__ll__client_8h_1a4e21aaa494a7ff52958e337551fde7eb) [Prov_Device_LL_SetOption](#prov__device__ll__client_8h_1ae5035b58c14ec28a988f90eee182f0fd)([PROV_DEVICE_LL_HANDLE](#prov__device__ll__client_8h_1aa6ce77119fc5a0c50d57a97a990cb54f) handle,const char * optionName,const void * value)

#### Prov_Device_LL_GetVersionString 
const char * [Prov_Device_LL_GetVersionString](#prov__device__ll__client_8h_1a3ba43fc4a5b83ec9e18f282745150f12)(void)

