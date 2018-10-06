# Map_Create()

Creates a new, empty map.

## Syntax

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/map.h](../iot-c-ref-map-h.md)"  
```C
MAP_HANDLE Map_Create(
  MAP_FILTER_CALLBACK  mapFilterFunc
);
```

## Parameters
* `mapFilterFunc` A callback function supplied by the caller that is invoked during calls to [Map_Add](#undefined) and [Map_AddOrUpdate](#undefined) to provide the caller an opportunity to indicate whether the new entry or the update to an existing entry can be made or not. The callback function can request that the operation be canceled by returning a non-zero value from the callback.

## Returns
A valid `MAP_HANDLE` or `NULL` in case an error occurs.

