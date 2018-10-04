# querySpecification_serializeToJson()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h"](../iot-c-ref-provisioning-sc-models-serializer-h.md)  

## Syntax

```C
char* querySpecification_serializeToJson(
  const   query_spec
);

```

Serializes a Query Specification into a JSON String.

#### Parameters
* `query_spec` A pointer to a Query Specification structure

#### Returns
A non NULL string containing the serialized JSON String, and NULL on failure.

