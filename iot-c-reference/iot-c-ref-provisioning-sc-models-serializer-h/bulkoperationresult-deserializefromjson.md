# bulkOperationResult_deserializeFromJson()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h"](../iot-c-ref-provisioning-sc-models-serializer-h.md)  

[`PROVISIONING_BULK_OPERATION_RESULT`](#struct_p_r_o_v_i_s_i_o_n_i_n_g___b_u_l_k___o_p_e_r_a_t_i_o_n___r_e_s_u_l_t) * `[`bulkOperationResult_deserializeFromJson`](#provisioning__sc__models__serializer_8h_1a19a49504727260e6adbe8643db3685b5)(const char * json_string)`

Deserializes a JSON String representation of a Bulk Operation Result.

#### Parameters
* `json_string` A JSON String representing an Bulk Operation Result.

#### Returns
A non-NULL pointer to a Bulk Operation Result and NULL on failure.

