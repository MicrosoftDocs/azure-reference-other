# json_serialize_and_set_struct()

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_shared_helpers.h](../iot-c-ref-provisioning-sc-shared-helpers-h.md)"  

## Syntax

```C
int json_serialize_and_set_struct(
  JSON_Object *     root_object,

  const char *      json_key,

  void *            structure,

  TO_JSON_FUNCTION  toJson,

  NECESSITY         necessity
);
```

