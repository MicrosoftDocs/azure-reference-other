# bulkOperation_serializeToJson()

Serializes a Bulk Operation into a JSON String.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h](../iot-c-ref-provisioning-sc-models-serializer-h.md)"  
```C
char* bulkOperation_serializeToJson(
  const   bulk_op
);
```

## Parameters
* `bulk_op` A pointer to a Bulk Operation structure

## Returns
A non-NULL string containing the serialized JSON String, and NULL on failure.

