# Map_GetInternals()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/map.h"](../iot-c-ref-map-h.md)  

[`MAP_RESULT`](#map_8h_1ad7dca46cbca14e08e0561d21ca68324e) `[`Map_GetInternals`](#map_8h_1ac97e499fa2f9b6830679e519185cd260)(`[`MAP_HANDLE`](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) handle,const char *const ** keys,const char *const ** values,size_t * count)`

Retrieves the complete list of keys and values from the map in `values` and `keys`. Also writes the size of the list in `count`.

#### Parameters
* `handle` The handle to an existing map. 

* `keys` The location where the list of keys is to be written. 

* `values` The location where the list of values is to be written. 

* `count` The number of stored keys and values is written at the location indicated by this pointer.

#### Returns
Returns `MAP_OK` if the keys and values are retrieved and written successfully or an error code otherwise.

