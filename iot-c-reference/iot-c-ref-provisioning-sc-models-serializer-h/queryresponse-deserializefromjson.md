# queryResponse_deserializeFromJson()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h"](../iot-c-ref-provisioning-sc-models-serializer-h.md)  

**[PROVISIONING_QUERY_RESPONSE](#struct_p_r_o_v_i_s_i_o_n_i_n_g___q_u_e_r_y___r_e_s_p_o_n_s_e) * [queryResponse_deserializeFromJson](#provisioning__sc__models__serializer_8h_1a19040dea100e85933243c0da80a51b21)(const char * json_string,[PROVISIONING_QUERY_TYPE](#provisioning__sc__query_8h_1ad692e96ac3865bb7733e30f2e895ed43) type)**

Deserializes a JSON String representation of a Query Response.

#### Parameters
* `json_string` A JSON String representing a Query Response. 

* `type` The type of model the query is being done upon

#### Returns
A non-NULL pointer to a Query Response and NULL on failure.

