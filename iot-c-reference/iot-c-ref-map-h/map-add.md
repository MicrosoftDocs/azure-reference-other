# Map_Add()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/map.h"](../iot-c-ref-map-h.md)  

## Syntax

```C
MAP_RESULT Map_Add(
  MAP_HANDLE	handle,
  const char *	key,
  const char *	value
);

```

Adds a key/value pair to the map.

#### Parameters
* `handle` The handle to an existing map. 

* `key` The `key` to be used for this map entry. 

* `value` The `value` to be associated with `key`.

If a non-NULL pointer to a callback function was supplied via the `mapFilterFunc` parameter when [Map_Create](#map_8h_1a76142fc262744d64715a597eac0ed9ff) was called then that callback is invoked when a new entry is added and if the callback returns a non-zero value then the function cancels the add operation and returns `MAP_FILTER_REJECT`.

#### Returns
If any of the input parameters are `NULL` then this function returns `MAP_INVALID_ARG`. If the key already exists in the map then `MAP_KEYEXISTS` is returned. If the filter function associated with the map rejects the entry then `MAP_FILTER_REJECT` is returned. In case an error occurs when the new key is added to the map the function returns `MAP_ERROR`. If everything goes well then `MAP_OK` is returned.

