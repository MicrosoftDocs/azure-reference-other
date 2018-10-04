# deviceRegistrationState_deserializeFromJson()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h"](../iot-c-ref-provisioning-sc-models-serializer-h.md)  

[`DEVICE_REGISTRATION_STATE_HANDLE`](#provisioning__sc__device__registration__state_8h_1a52841b38d699231f85846525109d2804) `[`deviceRegistrationState_deserializeFromJson`](#provisioning__sc__models__serializer_8h_1a2776a64371886fab2e21d3052ddca69b)(const char * json_string)`

Deserializes a JSON String representation of a Device Registration State.

#### Parameters
* `json_string` A JSON String representing a Device Registration State.

#### Returns
A non-NULL handle representing a Device Registration State, and NULL on failure.

