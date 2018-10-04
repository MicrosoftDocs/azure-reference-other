# Map_Clone()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/map.h"](../iot-c-ref-map-h.md)  

**[MAP_HANDLE](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) [Map_Clone](#map_8h_1acab6921eb142a4d60b1fc65f82b4432c)([MAP_HANDLE](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) handle)**

Creates a copy of the map indicated by `handle` and returns a handle to it.

#### Parameters
* `handle` The handle to an existing map.

#### Returns
A valid `MAP_HANDLE` to the cloned copy of the map or `NULL` in case an error occurs.

