# Map_Clone()

Creates a copy of the map indicated by handle and returns a handle to it.

## Syntax

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/map.h](../iot-c-ref-map-h.md)"  
```C
MAP_HANDLE Map_Clone(
  MAP_HANDLE  handle
);
```

## Parameters
* `handle` The handle to an existing map.

## Return Value
A valid MAP_HANDLE to the cloned copy of the map or NULL in case an error occurs.

