# individualEnrollment_deserializeFromJson()

Deserializes a JSON String representation of an Individual Enrollment.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h](../iot-c-ref-provisioning-sc-models-serializer-h.md)"  
```C
INDIVIDUAL_ENROLLMENT_HANDLE individualEnrollment_deserializeFromJson(
  const char *  json_string
);
```

## Parameters
* `json_string` A JSON String representing an Individual Enrollment.

## Return Value
A non-NULL handle representing an Individual Enrollment, and NULL on failure.

