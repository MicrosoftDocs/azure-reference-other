# enrollmentGroup_deserializeFromJson()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h"](../iot-c-ref-provisioning-sc-models-serializer-h.md)  

## Syntax

```C
ENROLLMENT_GROUP_HANDLE enrollmentGroup_deserializeFromJson(
  const char *  	json_string
);

```

Deserializes a JSON String representation of an Enrollment Group.

#### Parameters
* `json_string` A JSON String representing an Enrollment Group.

#### Returns
A non-NULL handle representing an Enrollment Group, and NULL on failure.

