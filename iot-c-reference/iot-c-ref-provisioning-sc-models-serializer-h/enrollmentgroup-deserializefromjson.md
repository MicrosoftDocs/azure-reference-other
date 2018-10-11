# enrollmentGroup_deserializeFromJson()

Deserializes a JSON String representation of an Enrollment Group.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h](../iot-c-ref-provisioning-sc-models-serializer-h.md)"  
```C
ENROLLMENT_GROUP_HANDLE enrollmentGroup_deserializeFromJson(
  const char *  json_string
);
```

## Parameters
* `json_string` A JSON String representing an Enrollment Group.

## Return Value
A non-NULL handle representing an Enrollment Group, and NULL on failure.

