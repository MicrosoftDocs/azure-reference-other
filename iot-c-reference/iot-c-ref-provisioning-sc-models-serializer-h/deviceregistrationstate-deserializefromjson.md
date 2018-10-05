# deviceRegistrationState_deserializeFromJson()

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h](../iot-c-ref-provisioning-sc-models-serializer-h.md)"  

## Syntax

```C
DEVICE_REGISTRATION_STATE_HANDLE deviceRegistrationState_deserializeFromJson(
  const char *  json_string
);
```

Deserializes a JSON String representation of a Device Registration State.

## Parameters
* **:json_string** A JSON String representing a Device Registration State.

## Returns
A non-NULL handle representing a Device Registration State, and NULL on failure.

