# bulkOperationResult_deserializeFromJson()

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h](../iot-c-ref-provisioning-sc-models-serializer-h.md)"  

## Syntax

```C
PROVISIONING_BULK_OPERATION_RESULT* bulkOperationResult_deserializeFromJson(
  const char *  json_string
);
```

Deserializes a JSON String representation of a Bulk Operation Result.

## Parameters
* `json_string`A JSON String representing an Bulk Operation Result.

## Returns
A non-NULL pointer to a Bulk Operation Result and NULL on failure.

