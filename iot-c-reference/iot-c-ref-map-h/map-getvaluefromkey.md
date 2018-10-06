# Map_GetValueFromKey()

Retrieves the value of a stored key.

## Syntax

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/map.h](../iot-c-ref-map-h.md)"  
```C
const char* Map_GetValueFromKey(
  MAP_HANDLE    handle,
  const char *  key
);
```

## Parameters
* `handle` The handle to an existing map. 

* `key` The key to be looked up in the map.

## Return Value
Returns `NULL` in case the input arguments are `NULL` or if the requested key is not found in the map. Returns a pointer to the key's value otherwise.

