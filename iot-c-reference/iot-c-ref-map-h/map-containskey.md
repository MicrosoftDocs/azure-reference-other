# Map_ContainsKey()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/map.h"](../iot-c-ref-map-h.md)  

[`MAP_RESULT`](#map_8h_1ad7dca46cbca14e08e0561d21ca68324e) `[`Map_ContainsKey`](#map_8h_1a766b6de5f152f5ba2669aa0832899e6d)(`[`MAP_HANDLE`](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) handle,const char * key,bool * keyExists)`

This function returns a boolean value in `keyExists` if the map contains a key with the same value the parameter `key`.

#### Parameters
* `handle` The handle to an existing map. 

* `key` The key that the caller wants checked. 

* `keyExists` The function writes `true` at the address pointed at by this parameter if the key exists in the map and `false` otherwise.

#### Returns
Returns `MAP_OK` if the check was performed successfully or an error code otherwise.

