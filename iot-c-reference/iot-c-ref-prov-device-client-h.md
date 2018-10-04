# Header file prov_device_client.h 

Extends the Prov_Device_LL module with additional features.

## Includes

\#include <stddef.h>  
\#include <stdint.h>  
\#include ["prov_device_ll_client.h"](iot-c-ref-prov-device-ll-client-h.md)  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_prov_client/prov_transport.h"](iot-c-ref-prov-transport-h.md)  

## Detailed Description

Prov_Device is a module that extends the Prov_Device_LL module with 2 features:

* scheduling the work for the IoTHubCLient from a thread, so that the user does not need to create their own thread

* thread-safe APIs

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[Prov_Device_Create](./iot-c-ref-prov-device-client-h/prov-device-create.md)            | 
[Prov_Device_Destroy](./iot-c-ref-prov-device-client-h/prov-device-destroy.md)            | 
[Prov_Device_Register_Device](./iot-c-ref-prov-device-client-h/prov-device-register-device.md)            | 
[Prov_Device_SetOption](./iot-c-ref-prov-device-client-h/prov-device-setoption.md)            | 
[Prov_Device_GetVersionString](./iot-c-ref-prov-device-client-h/prov-device-getversionstring.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
PROV_DEVICE_CLIENT_INSTANCE_TYPE            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
PROV_DEVICE_HANDLE            | 

## Function documentation

#### Prov_Device_Create 
[`PROV_DEVICE_HANDLE`](#prov__device__client_8h_1a24ef8c85c7bb0934f64a2365cd2c50a4) `[`Prov_Device_Create`](#prov__device__client_8h_1a86590df8321c4db049e116e6477f1e90)(const char * uri,const char * scope_id,`[`PROV_DEVICE_TRANSPORT_PROVIDER_FUNCTION`](#prov__device__ll__client_8h_1a6464d6b187cc71ac6e81938338d31d48) protocol)`

#### Prov_Device_Destroy 
void `[`Prov_Device_Destroy`](#prov__device__client_8h_1a614075e1a574d38618a98b7dafb4c992)(`[`PROV_DEVICE_HANDLE`](#prov__device__client_8h_1a24ef8c85c7bb0934f64a2365cd2c50a4) prov_device_handle)`

#### Prov_Device_Register_Device 
[`PROV_DEVICE_RESULT`](#prov__device__ll__client_8h_1a4e21aaa494a7ff52958e337551fde7eb) `[`Prov_Device_Register_Device`](#prov__device__client_8h_1a81497d39f567ce607a3d88be8efc25a1)(`[`PROV_DEVICE_HANDLE`](#prov__device__client_8h_1a24ef8c85c7bb0934f64a2365cd2c50a4) prov_device_handle,`[`PROV_DEVICE_CLIENT_REGISTER_DEVICE_CALLBACK`](#prov__device__ll__client_8h_1ac1a30031c36b065d7557ab76e919201f) register_callback,void * user_context,`[`PROV_DEVICE_CLIENT_REGISTER_STATUS_CALLBACK`](#prov__device__ll__client_8h_1a992c5a15ab87f820c87ca2121cb1fd14) register_status_callback,void * status_user_context)`

#### Prov_Device_SetOption 
[`PROV_DEVICE_RESULT`](#prov__device__ll__client_8h_1a4e21aaa494a7ff52958e337551fde7eb) `[`Prov_Device_SetOption`](#prov__device__client_8h_1aac96d42d27cdce7a0d415bafbdc54b30)(`[`PROV_DEVICE_HANDLE`](#prov__device__client_8h_1a24ef8c85c7bb0934f64a2365cd2c50a4) prov_device_handle,const char * optionName,const void * value)`

#### Prov_Device_GetVersionString 
const char * `[`Prov_Device_GetVersionString`](#prov__device__client_8h_1ad182914453b800ba8422b7d11c5d4891)(void)`

