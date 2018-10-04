# bulkOperation_serializeToJson()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h"](../iot-c-ref-provisioning-sc-models-serializer-h.md)  

char * `[`bulkOperation_serializeToJson`](#provisioning__sc__models__serializer_8h_1a2400110e7cd7c6909ee9e769db66d2c5)(const `[`PROVISIONING_BULK_OPERATION`](#struct_p_r_o_v_i_s_i_o_n_i_n_g___b_u_l_k___o_p_e_r_a_t_i_o_n) * bulk_op)`

Serializes a Bulk Operation into a JSON String.

#### Parameters
* `bulk_op` A pointer to a Bulk Operation structure

#### Returns
A non-NULL string containing the serialized JSON String, and NULL on failure.

