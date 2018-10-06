# bulkOperationResult_deserializeFromJson()

Deserializes a JSON String representation of a Bulk Operation Result.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h](../iot-c-ref-provisioning-sc-models-serializer-h.md)"  
```C
PROVISIONING_BULK_OPERATION_RESULT* bulkOperationResult_deserializeFromJson(
  const char *  json_string
);
```

## Parameters
* `json_string` A JSON String representing an Bulk Operation Result.

## Return Value
A non-NULL pointer to a Bulk Operation Result and NULL on failure.

