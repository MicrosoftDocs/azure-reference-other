# struct_array_fromJson()

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_shared_helpers.h](../iot-c-ref-provisioning-sc-shared-helpers-h.md)"  

## Syntax

```C
void** struct_array_fromJson(
  JSON_Array *        json_arr,
  size_t              len,
  FROM_JSON_FUNCTION  fromJson
);
```

