# Map_ContainsValue()

This function returns `true` in `valueExists` if at least one <key,value> pair exists in the map where the entry's value is equal to the parameter `value`.

## Syntax

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/map.h](../iot-c-ref-map-h.md)"  
```C
MAP_RESULT Map_ContainsValue(
  MAP_HANDLE    handle,
  const char *  value,
  bool *        valueExists
);
```

## Parameters
* `handle` The handle to an existing map. 

* `value` The value that the caller wants checked. 

* `valueExists` The function writes `true` at the address pointed at by this parameter if the value exists in the map and `false` otherwise.

## Return Value
Returns `MAP_OK` if the check was performed successfully or an error code otherwise.

