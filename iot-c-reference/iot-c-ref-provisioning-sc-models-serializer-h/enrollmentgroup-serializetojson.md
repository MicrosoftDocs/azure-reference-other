# enrollmentGroup_serializeToJson()

Serializes an Enrollment Group into a JSON String.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h](../iot-c-ref-provisioning-sc-models-serializer-h.md)"  
```C
char* enrollmentGroup_serializeToJson(
  const   enrollment
);
```

## Parameters
* `enrollment` A handle for the Enrollment Group to be serialized.

## Returns
A non-NULL string containing the serialized JSON String, and NULL on failure.

