# Header file provisioning_sc_query.h 

Stub comment for brief. Please update this comment.

## Includes

\#include <stdlib.h>  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["provisioning_sc_models.h"](iot-c-ref-provisioning-sc-models-h.md)  
\#include "parson.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[PROVISIONING_QUERY_TYPEStrings](./iot-c-ref-provisioning-sc-query-h/provisioning-query-typestrings.md)            | 
[PROVISIONING_QUERY_TYPE_FromString](./iot-c-ref-provisioning-sc-query-h/provisioning-query-type-fromstring.md)            | 
[queryResponse_free](./iot-c-ref-provisioning-sc-query-h/queryresponse-free.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
PROVISIONING_QUERY_SPECIFICATION_VERSION_1            | 
NO_MAX_PAGE_SIZE            | 
PROVISIONING_QUERY_TYPE_VALUES            | 

## Function documentation

#### PROVISIONING_QUERY_TYPEStrings 
const char * `[`PROVISIONING_QUERY_TYPEStrings`](#provisioning__sc__query_8h_1abe90e3e14bbf73c62f531ca48f820f52)(`[`PROVISIONING_QUERY_TYPE`](#provisioning__sc__query_8h_1ad692e96ac3865bb7733e30f2e895ed43) value)`

#### PROVISIONING_QUERY_TYPE_FromString 
int `[`PROVISIONING_QUERY_TYPE_FromString`](#provisioning__sc__query_8h_1a8195564681f7f3991c5183e721278fb6)(const char * enumAsString,`[`PROVISIONING_QUERY_TYPE`](#provisioning__sc__query_8h_1ad692e96ac3865bb7733e30f2e895ed43) * destination)`

#### queryResponse_free 
void `[`queryResponse_free`](#provisioning__sc__query_8h_1a36ae562350d9546b4f73fc63d34ccb36)(`[`PROVISIONING_QUERY_RESPONSE`](#struct_p_r_o_v_i_s_i_o_n_i_n_g___q_u_e_r_y___r_e_s_p_o_n_s_e) * query_resp)`

