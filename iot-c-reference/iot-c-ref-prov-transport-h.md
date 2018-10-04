# Header file prov_transport.h 

Stub comment for brief. Please update this comment.

## Includes

\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_c_shared_utility/shared_util_options.h"](iot-c-ref-shared-util-options-h.md)  
\#include "azure_c_shared_utility/buffer_.h"  
\#include <stdbool.h>  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[TRANSPORT_HSM_TYPEStrings](./iot-c-ref-prov-transport-h/transport-hsm-typestrings.md)            | 
[TRANSPORT_HSM_TYPE_FromString](./iot-c-ref-prov-transport-h/transport-hsm-type-fromstring.md)            | 
[PROV_DEVICE_TRANSPORT_RESULTStrings](./iot-c-ref-prov-transport-h/prov-device-transport-resultstrings.md)            | 
[PROV_DEVICE_TRANSPORT_RESULT_FromString](./iot-c-ref-prov-transport-h/prov-device-transport-result-fromstring.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
TRANSPORT_HSM_TYPE_VALUES            | 
PROV_DEVICE_TRANSPORT_RESULT_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
PROV_DEVICE_TRANSPORT_PROVIDER            | 
PROV_DEVICE_TRANSPORT_HANDLE            | 

## Function documentation

#### TRANSPORT_HSM_TYPEStrings 
const char * [TRANSPORT_HSM_TYPEStrings](#prov__transport_8h_1adb1e16090feacfd67af633af8caa4114)([TRANSPORT_HSM_TYPE](#prov__transport_8h_1a004b99d72c10223eed5aa9b23ea95905) value)

#### TRANSPORT_HSM_TYPE_FromString 
int [TRANSPORT_HSM_TYPE_FromString](#prov__transport_8h_1a2ab70c1b56f5261a4edebe022f03ffed)(const char * enumAsString,[TRANSPORT_HSM_TYPE](#prov__transport_8h_1a004b99d72c10223eed5aa9b23ea95905) * destination)

#### PROV_DEVICE_TRANSPORT_RESULTStrings 
const char * [PROV_DEVICE_TRANSPORT_RESULTStrings](#prov__transport_8h_1ae3c59192ee6bed7fc6e106784dac72e0)([PROV_DEVICE_TRANSPORT_RESULT](#prov__transport_8h_1acf3858785ecb5d22ae41ba72bba78797) value)

#### PROV_DEVICE_TRANSPORT_RESULT_FromString 
int [PROV_DEVICE_TRANSPORT_RESULT_FromString](#prov__transport_8h_1a624191c46a429a6700173821973ad950)(const char * enumAsString,[PROV_DEVICE_TRANSPORT_RESULT](#prov__transport_8h_1acf3858785ecb5d22ae41ba72bba78797) * destination)

