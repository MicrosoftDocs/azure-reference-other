# queryResponse_deserializeFromJson()

Deserializes a JSON String representation of a Query Response.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h](../iot-c-ref-provisioning-sc-models-serializer-h.md)"  
```C
PROVISIONING_QUERY_RESPONSE* queryResponse_deserializeFromJson(
  const char *             json_string,
  PROVISIONING_QUERY_TYPE  type
);
```

## Parameters
* `json_string` A JSON String representing a Query Response. 

* `type` The type of model the query is being done upon

## Returns
A non-NULL pointer to a Query Response and NULL on failure.

