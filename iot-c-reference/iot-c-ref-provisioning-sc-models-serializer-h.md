# Header file provisioning_sc_models_serializer.h 

Stub comment for brief. Please update this comment.

## Includes

\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["provisioning_sc_enrollment.h"](iot-c-ref-provisioning-sc-enrollment-h.md)  
\#include ["provisioning_sc_query.h"](iot-c-ref-provisioning-sc-query-h.md)  
\#include ["provisioning_sc_bulk_operation.h"](iot-c-ref-provisioning-sc-bulk-operation-h.md)  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[individualEnrollment_serializeToJson](./iot-c-ref-provisioning-sc-models-serializer-h/individualenrollment-serializetojson.md)            | Serializes an Individual Enrollment into a JSON String.
[individualEnrollment_deserializeFromJson](./iot-c-ref-provisioning-sc-models-serializer-h/individualenrollment-deserializefromjson.md)            | Deserializes a JSON String representation of an Individual Enrollment.
[enrollmentGroup_serializeToJson](./iot-c-ref-provisioning-sc-models-serializer-h/enrollmentgroup-serializetojson.md)            | Serializes an Enrollment Group into a JSON String.
[enrollmentGroup_deserializeFromJson](./iot-c-ref-provisioning-sc-models-serializer-h/enrollmentgroup-deserializefromjson.md)            | Deserializes a JSON String representation of an Enrollment Group.
[deviceRegistrationState_deserializeFromJson](./iot-c-ref-provisioning-sc-models-serializer-h/deviceregistrationstate-deserializefromjson.md)            | Deserializes a JSON String representation of a Device Registration State.
[bulkOperation_serializeToJson](./iot-c-ref-provisioning-sc-models-serializer-h/bulkoperation-serializetojson.md)            | Serializes a Bulk Operation into a JSON String.
[bulkOperationResult_deserializeFromJson](./iot-c-ref-provisioning-sc-models-serializer-h/bulkoperationresult-deserializefromjson.md)            | Deserializes a JSON String representation of a Bulk Operation Result.
[querySpecification_serializeToJson](./iot-c-ref-provisioning-sc-models-serializer-h/queryspecification-serializetojson.md)            | Serializes a Query Specification into a JSON String.
[queryResponse_deserializeFromJson](./iot-c-ref-provisioning-sc-models-serializer-h/queryresponse-deserializefromjson.md)            | Deserializes a JSON String representation of a Query Response.

## Function documentation

#### individualEnrollment_serializeToJson 
char * `[`individualEnrollment_serializeToJson`](#provisioning__sc__models__serializer_8h_1a9d9736511910a28158e9604bf867aee8)(const `[`INDIVIDUAL_ENROLLMENT_HANDLE`](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)`

#### individualEnrollment_deserializeFromJson 
[`INDIVIDUAL_ENROLLMENT_HANDLE`](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) `[`individualEnrollment_deserializeFromJson`](#provisioning__sc__models__serializer_8h_1a7aa3e180f40c1fb8b414c196333b0a78)(const char * json_string)`

#### enrollmentGroup_serializeToJson 
char * `[`enrollmentGroup_serializeToJson`](#provisioning__sc__models__serializer_8h_1a34aa155f69d90a364cf3a968448416cd)(const `[`ENROLLMENT_GROUP_HANDLE`](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment)`

#### enrollmentGroup_deserializeFromJson 
[`ENROLLMENT_GROUP_HANDLE`](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) `[`enrollmentGroup_deserializeFromJson`](#provisioning__sc__models__serializer_8h_1ae385a17e35fd22274b47441eaa5dd0dd)(const char * json_string)`

#### deviceRegistrationState_deserializeFromJson 
[`DEVICE_REGISTRATION_STATE_HANDLE`](#provisioning__sc__device__registration__state_8h_1a52841b38d699231f85846525109d2804) `[`deviceRegistrationState_deserializeFromJson`](#provisioning__sc__models__serializer_8h_1a2776a64371886fab2e21d3052ddca69b)(const char * json_string)`

#### bulkOperation_serializeToJson 
char * `[`bulkOperation_serializeToJson`](#provisioning__sc__models__serializer_8h_1a2400110e7cd7c6909ee9e769db66d2c5)(const `[`PROVISIONING_BULK_OPERATION`](#struct_p_r_o_v_i_s_i_o_n_i_n_g___b_u_l_k___o_p_e_r_a_t_i_o_n) * bulk_op)`

#### bulkOperationResult_deserializeFromJson 
[`PROVISIONING_BULK_OPERATION_RESULT`](#struct_p_r_o_v_i_s_i_o_n_i_n_g___b_u_l_k___o_p_e_r_a_t_i_o_n___r_e_s_u_l_t) * `[`bulkOperationResult_deserializeFromJson`](#provisioning__sc__models__serializer_8h_1a19a49504727260e6adbe8643db3685b5)(const char * json_string)`

#### querySpecification_serializeToJson 
char * `[`querySpecification_serializeToJson`](#provisioning__sc__models__serializer_8h_1aed39c4950fb4315e7668693da9c7b22b)(const `[`PROVISIONING_QUERY_SPECIFICATION`](#struct_p_r_o_v_i_s_i_o_n_i_n_g___q_u_e_r_y___s_p_e_c_i_f_i_c_a_t_i_o_n) * query_spec)`

#### queryResponse_deserializeFromJson 
[`PROVISIONING_QUERY_RESPONSE`](#struct_p_r_o_v_i_s_i_o_n_i_n_g___q_u_e_r_y___r_e_s_p_o_n_s_e) * `[`queryResponse_deserializeFromJson`](#provisioning__sc__models__serializer_8h_1a19040dea100e85933243c0da80a51b21)(const char * json_string,`[`PROVISIONING_QUERY_TYPE`](#provisioning__sc__query_8h_1ad692e96ac3865bb7733e30f2e895ed43) type)`

