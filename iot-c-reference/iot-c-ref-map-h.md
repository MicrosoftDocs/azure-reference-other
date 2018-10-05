# map.h 

Map is a module that implements a dictionary of `STRING_HANDLE` keys to `STRING_HANDLE` values.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include "[azure_c_shared_utility/strings.h](iot-c-ref-strings-h.md)"  
\#include "azure_c_shared_utility/crt_abstractions.h"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include <stddef.h>  

## Detailed Description

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[MAP_RESULTStrings](./iot-c-ref-map-h/map-resultstrings.md)            | 
[MAP_RESULT_FromString](./iot-c-ref-map-h/map-result-fromstring.md)            | 
[Map_Create](./iot-c-ref-map-h/map-create.md)            | Creates a new, empty map.
[Map_Destroy](./iot-c-ref-map-h/map-destroy.md)            | Release all resources associated with the map.
[Map_Clone](./iot-c-ref-map-h/map-clone.md)            | Creates a copy of the map indicated by `handle` and returns a handle to it.
[Map_Add](./iot-c-ref-map-h/map-add.md)            | Adds a key/value pair to the map.
[Map_AddOrUpdate](./iot-c-ref-map-h/map-addorupdate.md)            | Adds/updates a key/value pair to the map.
[Map_Delete](./iot-c-ref-map-h/map-delete.md)            | Removes a key and its associated value from the map.
[Map_ContainsKey](./iot-c-ref-map-h/map-containskey.md)            | This function returns a boolean value in `keyExists` if the map contains a key with the same value the parameter `key`.
[Map_ContainsValue](./iot-c-ref-map-h/map-containsvalue.md)            | This function returns `true` in `valueExists` if at least one <key,value> pair exists in the map where the entry's value is equal to the parameter `value`.
[Map_GetValueFromKey](./iot-c-ref-map-h/map-getvaluefromkey.md)            | Retrieves the value of a stored key.
[Map_GetInternals](./iot-c-ref-map-h/map-getinternals.md)            | Retrieves the complete list of keys and values from the map in `values` and `keys`. Also writes the size of the list in `count`.
[Map_ToJSON](./iot-c-ref-map-h/map-tojson.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
MAP_RESULT_VALUES            | 

## Typedefs

####MAP_HANDLE

```C
typedef struct MAP_HANDLE_DATA_TAG * MAP_HANDLE()

```

####MAP_FILTER_CALLBACK

```C
typedef int(* MAP_FILTER_CALLBACK()

```

