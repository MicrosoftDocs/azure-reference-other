# Header file provisioning_service_client.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include ["azure_c_shared_utility/shared_util_options.h"](iot-c-ref-shared-util-options-h.md)  
\#include ["provisioning_sc_models.h"](iot-c-ref-provisioning-sc-models-h.md)  
\#include ["provisioning_sc_query.h"](iot-c-ref-provisioning-sc-query-h.md)  
\#include ["provisioning_sc_bulk_operation.h"](iot-c-ref-provisioning-sc-bulk-operation-h.md)  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[TRACING_STATUSStrings](./iot-c-ref-provisioning-service-client-h/tracing-statusstrings.md)            | 
[TRACING_STATUS_FromString](./iot-c-ref-provisioning-service-client-h/tracing-status-fromstring.md)            | 
[prov_sc_create_from_connection_string](./iot-c-ref-provisioning-service-client-h/prov-sc-create-from-connection-string.md)            | Creates a Provisioning Service Client handle for use in consequent APIs.
[prov_sc_destroy](./iot-c-ref-provisioning-service-client-h/prov-sc-destroy.md)            | Disposes of resources allocated by creating a Provisioning Service Client handle.
[prov_sc_set_trace](./iot-c-ref-provisioning-service-client-h/prov-sc-set-trace.md)            | Sets tracing/logging of http communications on or off.
[prov_sc_set_certificate](./iot-c-ref-provisioning-service-client-h/prov-sc-set-certificate.md)            | Set the trusted certificate for HTTP communication with the Provisioning Service.
[prov_sc_set_proxy](./iot-c-ref-provisioning-service-client-h/prov-sc-set-proxy.md)            | Set the proxy options for HTTP communication with the Provisioning Service.
[prov_sc_create_or_update_individual_enrollment](./iot-c-ref-provisioning-service-client-h/prov-sc-create-or-update-individual-enrollment.md)            | Creates or updates an individual device enrollment record on the Provisioning Service, reflecting the changes in the given struct.
[prov_sc_delete_individual_enrollment](./iot-c-ref-provisioning-service-client-h/prov-sc-delete-individual-enrollment.md)            | Deletes a individual device enrollment record on the Provisioning Service.
[prov_sc_delete_individual_enrollment_by_param](./iot-c-ref-provisioning-service-client-h/prov-sc-delete-individual-enrollment-by-param.md)            | Deletes an individual device enrollment record on the Provisioning Service.
[prov_sc_get_individual_enrollment](./iot-c-ref-provisioning-service-client-h/prov-sc-get-individual-enrollment.md)            | Retreives an individual device enrollment record from the Provisioning Service.
[prov_sc_query_individual_enrollment](./iot-c-ref-provisioning-service-client-h/prov-sc-query-individual-enrollment.md)            | Queries individual device enrollment records from the Provisioning Service.
[prov_sc_run_individual_enrollment_bulk_operation](./iot-c-ref-provisioning-service-client-h/prov-sc-run-individual-enrollment-bulk-operation.md)            | Performs a bulk operation on individual device enrollment records from the provisioning service.
[prov_sc_create_or_update_enrollment_group](./iot-c-ref-provisioning-service-client-h/prov-sc-create-or-update-enrollment-group.md)            | Creates or updates a device enrollment group record on the Provisioning Service.
[prov_sc_delete_enrollment_group](./iot-c-ref-provisioning-service-client-h/prov-sc-delete-enrollment-group.md)            | Deletes a device enrollment group record on the Provisioning Service.
[prov_sc_delete_enrollment_group_by_param](./iot-c-ref-provisioning-service-client-h/prov-sc-delete-enrollment-group-by-param.md)            | Deletes a device enrollment group record on the Provisioning Service.
[prov_sc_get_enrollment_group](./iot-c-ref-provisioning-service-client-h/prov-sc-get-enrollment-group.md)            | Retreives a device enrollment group record from the Provisioning Service.
[prov_sc_query_enrollment_group](./iot-c-ref-provisioning-service-client-h/prov-sc-query-enrollment-group.md)            | Queries enrollment group records from the Provisioning Service.
[prov_sc_delete_device_registration_state](./iot-c-ref-provisioning-service-client-h/prov-sc-delete-device-registration-state.md)            | Deletes a device registration state on the Provisioning Service.
[prov_sc_delete_device_registration_state_by_param](./iot-c-ref-provisioning-service-client-h/prov-sc-delete-device-registration-state-by-param.md)            | Deletes a device registration state on the Provisioning Service.
[prov_sc_get_device_registration_state](./iot-c-ref-provisioning-service-client-h/prov-sc-get-device-registration-state.md)            | Retreives a device registration state from the Provisioning Service.
[prov_sc_query_device_registration_state](./iot-c-ref-provisioning-service-client-h/prov-sc-query-device-registration-state.md)            | Queries device registration state records from the Provisioning Service.

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
TRACING_STATUS_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
PROVISIONING_SERVICE_CLIENT_HANDLE            | Handle to hide struct and use it in consequent APIs.

## Function documentation

#### TRACING_STATUSStrings 
const char * [TRACING_STATUSStrings](#provisioning__service__client_8h_1a665bded8225c3603cb64975d1f4d9957)([TRACING_STATUS](#provisioning__service__client_8h_1a2b15150eb7be335527502632b5692150) value)

#### TRACING_STATUS_FromString 
int [TRACING_STATUS_FromString](#provisioning__service__client_8h_1a3de3068abee580adf23193012c5c7c64)(const char * enumAsString,[TRACING_STATUS](#provisioning__service__client_8h_1a2b15150eb7be335527502632b5692150) * destination)

#### prov_sc_create_from_connection_string 
[PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) [prov_sc_create_from_connection_string](#provisioning__service__client_8h_1a75fab11e046d9b645a8a094aefffd55c)(const char * conn_string)

#### prov_sc_destroy 
void [prov_sc_destroy](#provisioning__service__client_8h_1af56b025dfb210fedf3fe6343b8279e82)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client)

#### prov_sc_set_trace 
void [prov_sc_set_trace](#provisioning__service__client_8h_1a4ca9816fa1cf22a90ffcec443735f8f3)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,[TRACING_STATUS](#provisioning__service__client_8h_1a2b15150eb7be335527502632b5692150) status)

#### prov_sc_set_certificate 
int [prov_sc_set_certificate](#provisioning__service__client_8h_1a57eb08d07d4b31285aa22466b8f34039)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,const char * certificate)

#### prov_sc_set_proxy 
int [prov_sc_set_proxy](#provisioning__service__client_8h_1aaa19266190d48360bcd3185013f22496)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,[HTTP_PROXY_OPTIONS](#struct_h_t_t_p___p_r_o_x_y___o_p_t_i_o_n_s) * proxy_options)

#### prov_sc_create_or_update_individual_enrollment 
int [prov_sc_create_or_update_individual_enrollment](#provisioning__service__client_8h_1a6edae25ef4128a0d11c411e50ac70c69)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,[INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) * enrollment_ptr)

#### prov_sc_delete_individual_enrollment 
int [prov_sc_delete_individual_enrollment](#provisioning__service__client_8h_1a0400a08cea1573b1d46d27bc326e9726)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,[INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)

#### prov_sc_delete_individual_enrollment_by_param 
int [prov_sc_delete_individual_enrollment_by_param](#provisioning__service__client_8h_1adf594d7256c4917e0aa39e38731b58c2)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,const char * reg_id,const char * etag)

#### prov_sc_get_individual_enrollment 
int [prov_sc_get_individual_enrollment](#provisioning__service__client_8h_1a65e0cd1c2f31a73eb4417dd897467750)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,const char * reg_id,[INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) * enrollment_ptr)

#### prov_sc_query_individual_enrollment 
int [prov_sc_query_individual_enrollment](#provisioning__service__client_8h_1aab1e03ff466abc075a25baf64e2fa819)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,[PROVISIONING_QUERY_SPECIFICATION](#struct_p_r_o_v_i_s_i_o_n_i_n_g___q_u_e_r_y___s_p_e_c_i_f_i_c_a_t_i_o_n) * query_spec,char ** cont_token_ptr,[PROVISIONING_QUERY_RESPONSE](#struct_p_r_o_v_i_s_i_o_n_i_n_g___q_u_e_r_y___r_e_s_p_o_n_s_e) ** query_resp_ptr)

#### prov_sc_run_individual_enrollment_bulk_operation 
int [prov_sc_run_individual_enrollment_bulk_operation](#provisioning__service__client_8h_1a4b603c3287344d9bf85673c31245be05)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,[PROVISIONING_BULK_OPERATION](#struct_p_r_o_v_i_s_i_o_n_i_n_g___b_u_l_k___o_p_e_r_a_t_i_o_n) * bulk_op,[PROVISIONING_BULK_OPERATION_RESULT](#struct_p_r_o_v_i_s_i_o_n_i_n_g___b_u_l_k___o_p_e_r_a_t_i_o_n___r_e_s_u_l_t) ** bulk_res_ptr)

#### prov_sc_create_or_update_enrollment_group 
int [prov_sc_create_or_update_enrollment_group](#provisioning__service__client_8h_1a1b63f862fdde65f6f82e3b2cfc0cf9d0)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,[ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) * enrollment_ptr)

#### prov_sc_delete_enrollment_group 
int [prov_sc_delete_enrollment_group](#provisioning__service__client_8h_1a90e867f213b500a9bb4f7ed460574ea2)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,[ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment)

#### prov_sc_delete_enrollment_group_by_param 
int [prov_sc_delete_enrollment_group_by_param](#provisioning__service__client_8h_1a6bfe115c0c849e9fda60286f22abb882)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,const char * group_id,const char * etag)

#### prov_sc_get_enrollment_group 
int [prov_sc_get_enrollment_group](#provisioning__service__client_8h_1ab00d4929b1167f3e43e45f5856a48ee3)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,const char * group_id,[ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) * enrollment_ptr)

#### prov_sc_query_enrollment_group 
int [prov_sc_query_enrollment_group](#provisioning__service__client_8h_1a64ad87f7a96ea09a89323a1b83f40696)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,[PROVISIONING_QUERY_SPECIFICATION](#struct_p_r_o_v_i_s_i_o_n_i_n_g___q_u_e_r_y___s_p_e_c_i_f_i_c_a_t_i_o_n) * query_spec,char ** cont_token_ptr,[PROVISIONING_QUERY_RESPONSE](#struct_p_r_o_v_i_s_i_o_n_i_n_g___q_u_e_r_y___r_e_s_p_o_n_s_e) ** query_resp_ptr)

#### prov_sc_delete_device_registration_state 
int [prov_sc_delete_device_registration_state](#provisioning__service__client_8h_1a5928de9ba394895bf2dbf48d3e85543d)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,[DEVICE_REGISTRATION_STATE_HANDLE](#provisioning__sc__device__registration__state_8h_1a52841b38d699231f85846525109d2804) reg_state)

#### prov_sc_delete_device_registration_state_by_param 
int [prov_sc_delete_device_registration_state_by_param](#provisioning__service__client_8h_1a0afae62d00a4064cc8c639f4f27e5120)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,const char * reg_id,const char * etag)

#### prov_sc_get_device_registration_state 
int [prov_sc_get_device_registration_state](#provisioning__service__client_8h_1a7b9036be3cfe96fb3aec21801f9e5e8a)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,const char * reg_id,[DEVICE_REGISTRATION_STATE_HANDLE](#provisioning__sc__device__registration__state_8h_1a52841b38d699231f85846525109d2804) * reg_state_ptr)

#### prov_sc_query_device_registration_state 
int [prov_sc_query_device_registration_state](#provisioning__service__client_8h_1a360b7f2dad122e92ab2b3b76e58f6f5c)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,[PROVISIONING_QUERY_SPECIFICATION](#struct_p_r_o_v_i_s_i_o_n_i_n_g___q_u_e_r_y___s_p_e_c_i_f_i_c_a_t_i_o_n) * query_spec,char ** cont_token_ptr,[PROVISIONING_QUERY_RESPONSE](#struct_p_r_o_v_i_s_i_o_n_i_n_g___q_u_e_r_y___r_e_s_p_o_n_s_e) ** query_resp_ptr)

