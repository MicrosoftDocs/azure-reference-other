# Map_Clone()

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/map.h](../iot-c-ref-map-h.md)"  

## Syntax

```C
MAP_HANDLE Map_Clone(
  MAP_HANDLE  handle
);
```

Creates a copy of the map indicated by `handle` and returns a handle to it.

## Parameters
* `handle`The handle to an existing map.

## Returns
A valid `MAP_HANDLE` to the cloned copy of the map or `NULL` in case an error occurs.

