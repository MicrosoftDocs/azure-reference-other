# IoTHubMessage_SetDiagnosticPropertyData()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_message.h"](../iot-c-ref-iothub-message-h.md)  

[`IOTHUB_MESSAGE_RESULT`](#iothub__message_8h_1a9ecf3d22e0ef357c3e7eda387ea07f62) `[`IoTHubMessage_SetDiagnosticPropertyData`](#iothub__message_8h_1aa5244a4e3d077c11023fc84cabd09203)(`[`IOTHUB_MESSAGE_HANDLE`](#iothub__message_8h_1a98782b8f57e3f751b4f0196de946432c) iotHubMessageHandle,const `[`IOTHUB_MESSAGE_DIAGNOSTIC_PROPERTY_DATA`](#struct_i_o_t_h_u_b___m_e_s_s_a_g_e___d_i_a_g_n_o_s_t_i_c___p_r_o_p_e_r_t_y___d_a_t_a) * diagnosticData)`

Sets the DiagnosticData for the IOTHUB_MESSAGE_HANDLE. CAUTION: SDK user should not call it directly, it is for internal use only.

#### Parameters
* `iotHubMessageHandle` Handle to the message. 

* `diagnosticData` Pointer to the memory location of the diagnosticData

#### Returns
Returns IOTHUB_MESSAGE_OK if the DiagnosticData was set successfully or an error code otherwise.

