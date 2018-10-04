# individualEnrollment_serializeToJson()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h"](../iot-c-ref-provisioning-sc-models-serializer-h.md)  

## Syntax

```C
char* individualEnrollment_serializeToJson(
  const   enrollment
);

```

Serializes an Individual Enrollment into a JSON String.

#### Parameters
* `enrollment` A handle for the Individual Enrollment to be serialized.

#### Returns
A non-NULL string containing the serialized JSON String, and NULL on failure.

