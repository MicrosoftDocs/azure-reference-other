# provisioning_sc_shared_helpers.h 

Stub comment for brief. Please update this comment.

## Includes

\#include <stdlib.h>  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "parson.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[NECESSITYStrings](./iot-c-ref-provisioning-sc-shared-helpers-h/necessitystrings.md)            | 
[NECESSITY_FromString](./iot-c-ref-provisioning-sc-shared-helpers-h/necessity-fromstring.md)            | 
[mallocAndStrcpy_overwrite](./iot-c-ref-provisioning-sc-shared-helpers-h/mallocandstrcpy-overwrite.md)            | 
[copy_json_string_field](./iot-c-ref-provisioning-sc-shared-helpers-h/copy-json-string-field.md)            | 
[json_serialize_and_set_struct](./iot-c-ref-provisioning-sc-shared-helpers-h/json-serialize-and-set-struct.md)            | 
[json_deserialize_and_get_struct](./iot-c-ref-provisioning-sc-shared-helpers-h/json-deserialize-and-get-struct.md)            | 
[json_serialize_and_set_struct_array](./iot-c-ref-provisioning-sc-shared-helpers-h/json-serialize-and-set-struct-array.md)            | 
[json_deserialize_and_get_struct_array](./iot-c-ref-provisioning-sc-shared-helpers-h/json-deserialize-and-get-struct-array.md)            | 
[struct_array_fromJson](./iot-c-ref-provisioning-sc-shared-helpers-h/struct-array-fromjson.md)            | 

## Macro definitions

#### NECESSITY_VALUES

```C
#define NECESSITY_VALUES \
        REQUIRED, \
        OPTIONAL 
```

## Enumeration types

#### NECESSITY

```C
enum NECESSITY {
  REQUIRED,
  OPTIONAL
}
```
Constant                    | Description                                
----------------------------|----------------
 REQUIRED            | 
 OPTIONAL            | 

## Type definitions

#### TO_JSON_FUNCTION

```C
typedef JSON_Value*(* TO_JSON_FUNCTION) (
  void *handle
);
```

#### FROM_JSON_FUNCTION

```C
typedef void*(* FROM_JSON_FUNCTION) (
  JSON_Object *root_object
);
```

