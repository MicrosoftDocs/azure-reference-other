# Header file prov_security_factory.h 

Stub comment for brief. Please update this comment.

## Includes

\#include <stddef.h>  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include "azure_c_shared_utility/macro_utils.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[SECURE_DEVICE_TYPEStrings](./iot-c-ref-prov-security-factory-h/secure-device-typestrings.md)            | 
[SECURE_DEVICE_TYPE_FromString](./iot-c-ref-prov-security-factory-h/secure-device-type-fromstring.md)            | 
[prov_dev_security_init](./iot-c-ref-prov-security-factory-h/prov-dev-security-init.md)            | 
[prov_dev_security_deinit](./iot-c-ref-prov-security-factory-h/prov-dev-security-deinit.md)            | 
[prov_dev_security_get_type](./iot-c-ref-prov-security-factory-h/prov-dev-security-get-type.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
SECURE_DEVICE_TYPE_VALUES            | 

## Function documentation

#### SECURE_DEVICE_TYPEStrings 
const char * `[`SECURE_DEVICE_TYPEStrings`](#prov__security__factory_8h_1a38a7d29e9a443b033aa1e5c8d9910bf4)(`[`SECURE_DEVICE_TYPE`](#prov__security__factory_8h_1ac9a874828d8329a97691c34f2e8ffded) value)`

#### SECURE_DEVICE_TYPE_FromString 
int `[`SECURE_DEVICE_TYPE_FromString`](#prov__security__factory_8h_1af1cd029ffca27a3113dc56a7f83d28b5)(const char * enumAsString,`[`SECURE_DEVICE_TYPE`](#prov__security__factory_8h_1ac9a874828d8329a97691c34f2e8ffded) * destination)`

#### prov_dev_security_init 
int `[`prov_dev_security_init`](#prov__security__factory_8h_1ac141d348bb85dfb03f97d6730198a16d)(`[`SECURE_DEVICE_TYPE`](#prov__security__factory_8h_1ac9a874828d8329a97691c34f2e8ffded) hsm_type)`

#### prov_dev_security_deinit 
void `[`prov_dev_security_deinit`](#prov__security__factory_8h_1afddb4222ef2690b735504e363be057fe)(void)`

#### prov_dev_security_get_type 
[`SECURE_DEVICE_TYPE`](#prov__security__factory_8h_1ac9a874828d8329a97691c34f2e8ffded) `[`prov_dev_security_get_type`](#prov__security__factory_8h_1acbb2e91dc666d43b489fe902537df9d0)(void)`

