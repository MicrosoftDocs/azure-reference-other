# querySpecification_serializeToJson()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h"](../iot-c-ref-provisioning-sc-models-serializer-h.md)  

char * `[`querySpecification_serializeToJson`](#provisioning__sc__models__serializer_8h_1aed39c4950fb4315e7668693da9c7b22b)(const `[`PROVISIONING_QUERY_SPECIFICATION`](#struct_p_r_o_v_i_s_i_o_n_i_n_g___q_u_e_r_y___s_p_e_c_i_f_i_c_a_t_i_o_n) * query_spec)`

Serializes a Query Specification into a JSON String.

#### Parameters
* `query_spec` A pointer to a Query Specification structure

#### Returns
A non NULL string containing the serialized JSON String, and NULL on failure.

