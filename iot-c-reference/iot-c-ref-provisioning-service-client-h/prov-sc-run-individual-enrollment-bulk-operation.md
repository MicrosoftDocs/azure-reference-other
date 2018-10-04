# prov_sc_run_individual_enrollment_bulk_operation()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

int `[`prov_sc_run_individual_enrollment_bulk_operation`](#provisioning__service__client_8h_1a4b603c3287344d9bf85673c31245be05)(`[`PROVISIONING_SERVICE_CLIENT_HANDLE`](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,`[`PROVISIONING_BULK_OPERATION`](#struct_p_r_o_v_i_s_i_o_n_i_n_g___b_u_l_k___o_p_e_r_a_t_i_o_n) * bulk_op,`[`PROVISIONING_BULK_OPERATION_RESULT`](#struct_p_r_o_v_i_s_i_o_n_i_n_g___b_u_l_k___o_p_e_r_a_t_i_o_n___r_e_s_u_l_t) ** bulk_res_ptr)`

Performs a bulk operation on individual device enrollment records from the provisioning service.

#### Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `bulk_op` A pointer to a bulk operation structure with details about the bulk operation. 

* `bulk_res_ptr` A pointer to a bulk operation result pointer that will be filled with the results upon completion

#### Returns
0 upon success, a non-zero number upon failure.

