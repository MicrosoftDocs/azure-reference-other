# Map_Create()

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/map.h](../iot-c-ref-map-h.md)"  

## Syntax

```C
MAP_HANDLE Map_Create(
  MAP_FILTER_CALLBACK  mapFilterFunc
);
```

Creates a new, empty map.

## Parameters
* **:mapFilterFunc** A callback function supplied by the caller that is invoked during calls to [Map_Add](#map_8h_1a0dd145d19021b3e80d53868d61cbc684) and [Map_AddOrUpdate](#map_8h_1a3c232f8741686b794a1a767117012497) to provide the caller an opportunity to indicate whether the new entry or the update to an existing entry can be made or not. The callback function can request that the operation be canceled by returning a non-zero value from the callback.

## Returns
A valid `MAP_HANDLE` or `NULL` in case an error occurs.

