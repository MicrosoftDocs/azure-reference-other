# json_deserialize_and_get_struct()

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_shared_helpers.h](../iot-c-ref-provisioning-sc-shared-helpers-h.md)"  

## Syntax

```C
int json_deserialize_and_get_struct(
  void **             dest,

  JSON_Object *       root_object,

  const char *        json_key,

  FROM_JSON_FUNCTION  fromJson,

  NECESSITY           necessity
);
```

