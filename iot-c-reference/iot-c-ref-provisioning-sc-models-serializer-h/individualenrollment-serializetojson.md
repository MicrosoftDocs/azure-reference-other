# individualEnrollment_serializeToJson()

Serializes an Individual Enrollment into a JSON String.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h](../iot-c-ref-provisioning-sc-models-serializer-h.md)"  
```C
char* individualEnrollment_serializeToJson(
  const   enrollment
);
```

## Parameters
* `enrollment` A handle for the Individual Enrollment to be serialized.

## Return Value
A non-NULL string containing the serialized JSON String, and NULL on failure.

