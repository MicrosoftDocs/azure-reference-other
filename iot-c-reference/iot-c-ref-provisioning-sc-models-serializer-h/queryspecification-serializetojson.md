# querySpecification_serializeToJson()

Serializes a Query Specification into a JSON String.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h](../iot-c-ref-provisioning-sc-models-serializer-h.md)"  
```C
char* querySpecification_serializeToJson(
  const   query_spec
);
```

## Parameters
* `query_spec` A pointer to a Query Specification structure

## Return Value
A non NULL string containing the serialized JSON String, and NULL on failure.

