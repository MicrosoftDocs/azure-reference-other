# Map_ContainsValue()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/map.h"](../iot-c-ref-map-h.md)  

**[MAP_RESULT](#map_8h_1ad7dca46cbca14e08e0561d21ca68324e) [Map_ContainsValue](#map_8h_1a6eda13c2772c352e0a39730a3ea77dc1)([MAP_HANDLE](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) handle,const char * value,bool * valueExists)**

This function returns `true` in `valueExists` if at least one <key,value> pair exists in the map where the entry's value is equal to the parameter `value`.

#### Parameters
* `handle` The handle to an existing map. 

* `value` The value that the caller wants checked. 

* `valueExists` The function writes `true` at the address pointed at by this parameter if the value exists in the map and `false` otherwise.

#### Returns
Returns `MAP_OK` if the check was performed successfully or an error code otherwise.

