# IoTHubMessage_GetDiagnosticPropertyData()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

const [`IOTHUB_MESSAGE_DIAGNOSTIC_PROPERTY_DATA`](#struct_i_o_t_h_u_b___m_e_s_s_a_g_e___d_i_a_g_n_o_s_t_i_c___p_r_o_p_e_r_t_y___d_a_t_a) * `[`IoTHubMessage_GetDiagnosticPropertyData`](#iothub__message_8h_1af9a6a0e67384e6194a5d3fde2dd149e9)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle)`

Gets the DiagnosticData from the IOTHUB_MESSAGE_HANDLE. CAUTION: SDK user should not call it directly, it is for internal use only.

#### Parameters
* `iotHubMessageHandle` Handle to the message.

#### Returns
A const IOTHUB_MESSAGE_DIAGNOSTIC_PROPERTY_DATA* pointing to the diagnostic property data.

