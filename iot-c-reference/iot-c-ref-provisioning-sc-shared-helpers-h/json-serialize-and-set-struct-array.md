# json_serialize_and_set_struct_array()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_shared_helpers.h"](../iot-c-ref-provisioning-sc-shared-helpers-h.md)  

## Syntax

```C
int json_serialize_and_set_struct_array(
  JSON_Object *	root_object,
  const char *	json_key,
  void **	arr,
  size_t	len,
  TO_JSON_FUNCTION	element_toJson
);

```

