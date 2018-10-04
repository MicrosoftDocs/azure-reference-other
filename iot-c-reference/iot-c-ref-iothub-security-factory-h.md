# Header file iothub_security_factory.h 

Stub comment for brief. Please update this comment.

## Includes

\#include <stddef.h>  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include "azure_c_shared_utility/buffer_.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IOTHUB_SECURITY_TYPEStrings](./iot-c-ref-iothub-security-factory-h/iothub-security-typestrings.md)            | 
[IOTHUB_SECURITY_TYPE_FromString](./iot-c-ref-iothub-security-factory-h/iothub-security-type-fromstring.md)            | 
[iothub_security_init](./iot-c-ref-iothub-security-factory-h/iothub-security-init.md)            | 
[iothub_security_deinit](./iot-c-ref-iothub-security-factory-h/iothub-security-deinit.md)            | 
[iothub_security_interface](./iot-c-ref-iothub-security-factory-h/iothub-security-interface.md)            | 
[iothub_security_type](./iot-c-ref-iothub-security-factory-h/iothub-security-type.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IOTHUB_SECURITY_TYPE_VALUES            | 

## Function documentation

#### IOTHUB_SECURITY_TYPEStrings 
const char * `[`IOTHUB_SECURITY_TYPEStrings`](#iothub__security__factory_8h_1a58dd380fd994a538c330ed1ca83e5a2e)(`[`IOTHUB_SECURITY_TYPE`](#iothub__security__factory_8h_1ad17f26cc00ddd30e6cdafdd681c332a2) value)`

#### IOTHUB_SECURITY_TYPE_FromString 
int `[`IOTHUB_SECURITY_TYPE_FromString`](#iothub__security__factory_8h_1a2b7abfa9a4888ed45cf24183df122fcc)(const char * enumAsString,`[`IOTHUB_SECURITY_TYPE`](#iothub__security__factory_8h_1ad17f26cc00ddd30e6cdafdd681c332a2) * destination)`

#### iothub_security_init 
int `[`iothub_security_init`](#iothub__security__factory_8h_1a93060186357fb9e1abd84a0ac682b57f)(`[`IOTHUB_SECURITY_TYPE`](#iothub__security__factory_8h_1ad17f26cc00ddd30e6cdafdd681c332a2) sec_type)`

#### iothub_security_deinit 
void `[`iothub_security_deinit`](#iothub__security__factory_8h_1a7875647eae3e0ce1fabcb0113e263143)(void)`

#### iothub_security_interface 
const void * `[`iothub_security_interface`](#iothub__security__factory_8h_1a9d7214333f3f7b666e7ee3a34fdcffb3)(void)`

#### iothub_security_type 
[`IOTHUB_SECURITY_TYPE`](#iothub__security__factory_8h_1ad17f26cc00ddd30e6cdafdd681c332a2) `[`iothub_security_type`](#iothub__security__factory_8h_1af07de36aba7f4122b3ccec9d6da94762)(void)`

