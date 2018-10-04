# Header file provisioning_sc_shared_helpers.h 

Stub comment for brief. Please update this comment.

## Includes

\#include <stdlib.h>  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include "parson.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[NECESSITYStrings](./iot-c-ref-provisioning-sc-shared-helpers-h/necessitystrings.md)            | 
[NECESSITY_FromString](./iot-c-ref-provisioning-sc-shared-helpers-h/necessity-fromstring.md)            | 
[mallocAndStrcpy_overwrite](./iot-c-ref-provisioning-sc-shared-helpers-h/mallocandstrcpy-overwrite.md)            | 
[copy_json_string_field](./iot-c-ref-provisioning-sc-shared-helpers-h/copy-json-string-field.md)            | 
[json_serialize_and_set_struct](./iot-c-ref-provisioning-sc-shared-helpers-h/json-serialize-and-set-struct.md)            | 
[json_deserialize_and_get_struct](./iot-c-ref-provisioning-sc-shared-helpers-h/json-deserialize-and-get-struct.md)            | 
[json_serialize_and_set_struct_array](./iot-c-ref-provisioning-sc-shared-helpers-h/json-serialize-and-set-struct-array.md)            | 
[json_deserialize_and_get_struct_array](./iot-c-ref-provisioning-sc-shared-helpers-h/json-deserialize-and-get-struct-array.md)            | 
[struct_array_fromJson](./iot-c-ref-provisioning-sc-shared-helpers-h/struct-array-fromjson.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
NECESSITY_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
TO_JSON_FUNCTION            | 
FROM_JSON_FUNCTION            | 

## Function documentation

#### NECESSITYStrings 
const char * `[`NECESSITYStrings`](#provisioning__sc__shared__helpers_8h_1a99fd0ce0dd970dd966d43f341dda71bd)(`[`NECESSITY`](#provisioning__sc__shared__helpers_8h_1aca964653ac17c5ef1c2c05da4907c7f9) value)`

#### NECESSITY_FromString 
int `[`NECESSITY_FromString`](#provisioning__sc__shared__helpers_8h_1a371deb12e767ab09a9a819ff4b41f16d)(const char * enumAsString,`[`NECESSITY`](#provisioning__sc__shared__helpers_8h_1aca964653ac17c5ef1c2c05da4907c7f9) * destination)`

#### mallocAndStrcpy_overwrite 
int `[`mallocAndStrcpy_overwrite`](#provisioning__sc__shared__helpers_8h_1a056c1badc6e1fca3a1e6e84aa95a3d2a)(char ** dest,const char * source)`

#### copy_json_string_field 
int `[`copy_json_string_field`](#provisioning__sc__shared__helpers_8h_1a67afe8f716b1a303c5e454da0f4adcd7)(char ** dest,JSON_Object * root_object,const char * json_key)`

#### json_serialize_and_set_struct 
int `[`json_serialize_and_set_struct`](#provisioning__sc__shared__helpers_8h_1ae12c1015a467d413c48505334de4ee2b)(JSON_Object * root_object,const char * json_key,void * structure,`[`TO_JSON_FUNCTION`](#provisioning__sc__shared__helpers_8h_1a6862df5b929925677f9d6268950c9e9c) toJson,`[`NECESSITY`](#provisioning__sc__shared__helpers_8h_1aca964653ac17c5ef1c2c05da4907c7f9) necessity)`

#### json_deserialize_and_get_struct 
int `[`json_deserialize_and_get_struct`](#provisioning__sc__shared__helpers_8h_1a497ca31c9fe119825c0afc1cdd425e0a)(void ** dest,JSON_Object * root_object,const char * json_key,`[`FROM_JSON_FUNCTION`](#provisioning__sc__shared__helpers_8h_1a136b203a128307c6c486bc77e747d51e) fromJson,`[`NECESSITY`](#provisioning__sc__shared__helpers_8h_1aca964653ac17c5ef1c2c05da4907c7f9) necessity)`

#### json_serialize_and_set_struct_array 
int `[`json_serialize_and_set_struct_array`](#provisioning__sc__shared__helpers_8h_1a2c9302d38ad5c5026cc6ca374322b218)(JSON_Object * root_object,const char * json_key,void ** arr,size_t len,`[`TO_JSON_FUNCTION`](#provisioning__sc__shared__helpers_8h_1a6862df5b929925677f9d6268950c9e9c) element_toJson)`

#### json_deserialize_and_get_struct_array 
int `[`json_deserialize_and_get_struct_array`](#provisioning__sc__shared__helpers_8h_1a007f45ade260834bf214aa13763a07f9)(void *** dest_arr,size_t * dest_len,JSON_Object * root_object,const char * json_key,`[`FROM_JSON_FUNCTION`](#provisioning__sc__shared__helpers_8h_1a136b203a128307c6c486bc77e747d51e) element_fromJson)`

#### struct_array_fromJson 
void ** `[`struct_array_fromJson`](#provisioning__sc__shared__helpers_8h_1ae157833edfa3bafad789527e3c84e180)(JSON_Array * json_arr,size_t len,`[`FROM_JSON_FUNCTION`](#provisioning__sc__shared__helpers_8h_1a136b203a128307c6c486bc77e747d51e) fromJson)`

