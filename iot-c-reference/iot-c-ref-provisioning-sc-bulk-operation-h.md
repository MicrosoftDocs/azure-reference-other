# Header file provisioning_sc_bulk_operation.h 

Stub comment for brief. Please update this comment.

## Includes

\#include <stdlib.h>  
\#include <stdint.h>  
\#include <stdbool.h>  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["provisioning_sc_models.h"](iot-c-ref-provisioning-sc-models-h.md)  
\#include "parson.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[PROVISIONING_BULK_OPERATION_MODEStrings](./iot-c-ref-provisioning-sc-bulk-operation-h/provisioning-bulk-operation-modestrings.md)            | 
[PROVISIONING_BULK_OPERATION_MODE_FromString](./iot-c-ref-provisioning-sc-bulk-operation-h/provisioning-bulk-operation-mode-fromstring.md)            | 
[PROVISIONING_BULK_OPERATION_TYPEStrings](./iot-c-ref-provisioning-sc-bulk-operation-h/provisioning-bulk-operation-typestrings.md)            | 
[PROVISIONING_BULK_OPERATION_TYPE_FromString](./iot-c-ref-provisioning-sc-bulk-operation-h/provisioning-bulk-operation-type-fromstring.md)            | 
[bulkOperationResult_free](./iot-c-ref-provisioning-sc-bulk-operation-h/bulkoperationresult-free.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
PROVISIONING_BULK_OPERATION_VERSION_1            | 
PROVISIONING_BULK_OPERATION_MODE_VALUES            | 
PROVISIONING_BULK_OPERATION_TYPE_VALUES            | 

## Function documentation

#### PROVISIONING_BULK_OPERATION_MODEStrings 
const char * [PROVISIONING_BULK_OPERATION_MODEStrings](#provisioning__sc__bulk__operation_8h_1a6ceb073de778931a7cc7277c3ed4beb2)([PROVISIONING_BULK_OPERATION_MODE](#provisioning__sc__bulk__operation_8h_1a1bc5c700455002be35a5b48f1a3f9e20) value)

#### PROVISIONING_BULK_OPERATION_MODE_FromString 
int [PROVISIONING_BULK_OPERATION_MODE_FromString](#provisioning__sc__bulk__operation_8h_1acf7326ee31ebdad31ce84015ce23d9bb)(const char * enumAsString,[PROVISIONING_BULK_OPERATION_MODE](#provisioning__sc__bulk__operation_8h_1a1bc5c700455002be35a5b48f1a3f9e20) * destination)

#### PROVISIONING_BULK_OPERATION_TYPEStrings 
const char * [PROVISIONING_BULK_OPERATION_TYPEStrings](#provisioning__sc__bulk__operation_8h_1af5a936d40aa961f6226eb9d42350a46f)([PROVISIONING_BULK_OPERATION_TYPE](#provisioning__sc__bulk__operation_8h_1ac66e6772e50bfc17920ea61fe3494f0d) value)

#### PROVISIONING_BULK_OPERATION_TYPE_FromString 
int [PROVISIONING_BULK_OPERATION_TYPE_FromString](#provisioning__sc__bulk__operation_8h_1a17d3b14bbba2a820e238e5356e2df96f)(const char * enumAsString,[PROVISIONING_BULK_OPERATION_TYPE](#provisioning__sc__bulk__operation_8h_1ac66e6772e50bfc17920ea61fe3494f0d) * destination)

#### bulkOperationResult_free 
void [bulkOperationResult_free](#provisioning__sc__bulk__operation_8h_1a4c4874d1c0b83cf507598225fbf1cb92)([PROVISIONING_BULK_OPERATION_RESULT](#struct_p_r_o_v_i_s_i_o_n_i_n_g___b_u_l_k___o_p_e_r_a_t_i_o_n___r_e_s_u_l_t) * bulk_op_result)

