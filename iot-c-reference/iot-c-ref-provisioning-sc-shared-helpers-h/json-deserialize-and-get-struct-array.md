# json_deserialize_and_get_struct_array()

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_shared_helpers.h](../iot-c-ref-provisioning-sc-shared-helpers-h.md)"  

## Syntax

```C
int json_deserialize_and_get_struct_array(
  void ***            dest_arr,
  size_t *            dest_len,
  JSON_Object *       root_object,
  const char *        json_key,
  FROM_JSON_FUNCTION  element_fromJson);
```

