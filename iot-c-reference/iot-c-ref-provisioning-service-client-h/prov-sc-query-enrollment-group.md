# prov_sc_query_enrollment_group()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

int `[`prov_sc_query_enrollment_group`](#provisioning__service__client_8h_1a64ad87f7a96ea09a89323a1b83f40696)(`[`PROVISIONING_SERVICE_CLIENT_HANDLE`](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,`[`PROVISIONING_QUERY_SPECIFICATION`](#struct_p_r_o_v_i_s_i_o_n_i_n_g___q_u_e_r_y___s_p_e_c_i_f_i_c_a_t_i_o_n) * query_spec,char ** cont_token_ptr,`[`PROVISIONING_QUERY_RESPONSE`](#struct_p_r_o_v_i_s_i_o_n_i_n_g___q_u_e_r_y___r_e_s_p_o_n_s_e) ** query_resp_ptr)`

Queries enrollment group records from the Provisioning Service.

#### Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `query_spec` The query specification with query details and settings 

* `cont_token_ptr` A pointer to a continuation token, which will be updated based on the response 

* `query_resp_ptr` A pointer to a query response pointer, which will be filled with retrieved data

#### Returns
0 upon success, a non-zero number upon failure

