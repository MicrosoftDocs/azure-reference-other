# Map_Delete()

Removes a key and its associated value from the map.

## Syntax

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/map.h](../iot-c-ref-map-h.md)"  
```C
MAP_RESULT Map_Delete(
  MAP_HANDLE    handle,
  const char *  key
);
```

## Parameters
* `handle` The handle to an existing map. 

* `key` The `key` of the item to be deleted.

## Returns
Returns `MAP_OK` if the key was deleted successfully or an error code otherwise.

