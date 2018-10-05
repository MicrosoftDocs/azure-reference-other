# Map_GetInternals()

Retrieves the complete list of keys and values from the map in `values` and `keys`. Also writes the size of the list in `count`.

## Syntax

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/map.h](../iot-c-ref-map-h.md)"  
```C
MAP_RESULT Map_GetInternals(
  MAP_HANDLE            handle,
  const char *const **  keys,
  const char *const **  values,
  size_t *              count
);
```

## Parameters
* `handle` The handle to an existing map. 

* `keys` The location where the list of keys is to be written. 

* `values` The location where the list of values is to be written. 

* `count` The number of stored keys and values is written at the location indicated by this pointer.

## Returns
Returns `MAP_OK` if the keys and values are retrieved and written successfully or an error code otherwise.

