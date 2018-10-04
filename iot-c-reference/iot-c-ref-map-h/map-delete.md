# Map_Delete()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/map.h"](../iot-c-ref-map-h.md)  

**[MAP_RESULT](#map_8h_1ad7dca46cbca14e08e0561d21ca68324e) [Map_Delete](#map_8h_1a6b188091de3ebf1f201197312d79bb61)([MAP_HANDLE](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) handle,const char * key)**

Removes a key and its associated value from the map.

#### Parameters
* `handle` The handle to an existing map. 

* `key` The `key` of the item to be deleted.

#### Returns
Returns `MAP_OK` if the key was deleted successfully or an error code otherwise.

