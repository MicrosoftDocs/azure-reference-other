# Header file map.h 

Map is a module that implements a dictionary of `STRING_HANDLE` keys to `STRING_HANDLE` values.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_c_shared_utility/strings.h"](iot-c-ref-strings-h.md)  
\#include "azure_c_shared_utility/crt_abstractions.h"  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
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

Typedef                        | Value                                
--------------------------------|---------------------------------------------
MAP_HANDLE            | 
MAP_FILTER_CALLBACK            | 

## Function documentation

#### MAP_RESULTStrings 
const char * [MAP_RESULTStrings](#map_8h_1acd22a0416776128bca9a3ef88e4624e3)([MAP_RESULT](#map_8h_1ad7dca46cbca14e08e0561d21ca68324e) value)

#### MAP_RESULT_FromString 
int [MAP_RESULT_FromString](#map_8h_1a5571c37e878b3829d11dc1900ad69e39)(const char * enumAsString,[MAP_RESULT](#map_8h_1ad7dca46cbca14e08e0561d21ca68324e) * destination)

#### Map_Create 
[MAP_HANDLE](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) [Map_Create](#map_8h_1a76142fc262744d64715a597eac0ed9ff)([MAP_FILTER_CALLBACK](#map_8h_1a0283d18ae29a5d4f2a68fe7a7c625462) mapFilterFunc)

#### Map_Destroy 
void [Map_Destroy](#map_8h_1a5a39e57aff544ff7880294b32233366b)([MAP_HANDLE](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) handle)

#### Map_Clone 
[MAP_HANDLE](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) [Map_Clone](#map_8h_1acab6921eb142a4d60b1fc65f82b4432c)([MAP_HANDLE](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) handle)

#### Map_Add 
[MAP_RESULT](#map_8h_1ad7dca46cbca14e08e0561d21ca68324e) [Map_Add](#map_8h_1a0dd145d19021b3e80d53868d61cbc684)([MAP_HANDLE](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) handle,const char * key,const char * value)

#### Map_AddOrUpdate 
[MAP_RESULT](#map_8h_1ad7dca46cbca14e08e0561d21ca68324e) [Map_AddOrUpdate](#map_8h_1a3c232f8741686b794a1a767117012497)([MAP_HANDLE](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) handle,const char * key,const char * value)

#### Map_Delete 
[MAP_RESULT](#map_8h_1ad7dca46cbca14e08e0561d21ca68324e) [Map_Delete](#map_8h_1a6b188091de3ebf1f201197312d79bb61)([MAP_HANDLE](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) handle,const char * key)

#### Map_ContainsKey 
[MAP_RESULT](#map_8h_1ad7dca46cbca14e08e0561d21ca68324e) [Map_ContainsKey](#map_8h_1a766b6de5f152f5ba2669aa0832899e6d)([MAP_HANDLE](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) handle,const char * key,bool * keyExists)

#### Map_ContainsValue 
[MAP_RESULT](#map_8h_1ad7dca46cbca14e08e0561d21ca68324e) [Map_ContainsValue](#map_8h_1a6eda13c2772c352e0a39730a3ea77dc1)([MAP_HANDLE](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) handle,const char * value,bool * valueExists)

#### Map_GetValueFromKey 
const char * [Map_GetValueFromKey](#map_8h_1a80f89a52adc845f206f8fa83951ffab3)([MAP_HANDLE](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) handle,const char * key)

#### Map_GetInternals 
[MAP_RESULT](#map_8h_1ad7dca46cbca14e08e0561d21ca68324e) [Map_GetInternals](#map_8h_1ac97e499fa2f9b6830679e519185cd260)([MAP_HANDLE](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) handle,const char *const ** keys,const char *const ** values,size_t * count)

#### Map_ToJSON 
[STRING_HANDLE](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) [Map_ToJSON](#map_8h_1a18439ab7eeb29aef68e3d18e32ad8abe)([MAP_HANDLE](#map_8h_1aaa6ea96fbf2e858b6b2cfe4c7fe31a46) handle)

