# provisioning_sc_query.h 

Stub comment for brief. Please update this comment.

## Includes

\#include <stdlib.h>  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include "[provisioning_sc_models.h](iot-c-ref-provisioning-sc-models-h.md)"  
\#include "parson.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[PROVISIONING_QUERY_TYPEStrings](./iot-c-ref-provisioning-sc-query-h/provisioning-query-typestrings.md)            | 
[PROVISIONING_QUERY_TYPE_FromString](./iot-c-ref-provisioning-sc-query-h/provisioning-query-type-fromstring.md)            | 
[queryResponse_free](./iot-c-ref-provisioning-sc-query-h/queryresponse-free.md)            | 

## Structures

#### PROVISIONING_QUERY_SPECIFICATION

```C
struct PROVISIONING_QUERY_SPECIFICATION {
  int           version,
  const char *  query_string,
  const char *  registration_id,
  size_t        page_size
};
```
#### PROVISIONING_QUERY_RESPONSE

```C
struct PROVISIONING_QUERY_RESPONSE {
  union PROVISIONING_QUERY_RESPONSE::@1  response_arr,
  size_t                                 response_arr_size,
  PROVISIONING_QUERY_TYPE                response_arr_type
};
```

## Macro definitions

#### PROVISIONING_QUERY_SPECIFICATION_VERSION_1

```C
#define PROVISIONING_QUERY_SPECIFICATION_VERSION_1 1 

```

#### NO_MAX_PAGE_SIZE

```C
#define NO_MAX_PAGE_SIZE 0 

```

#### PROVISIONING_QUERY_TYPE_VALUES

```C
#define PROVISIONING_QUERY_TYPE_VALUES \
 QUERY_TYPE_INVALID, \
 QUERY_TYPE_INDIVIDUAL_ENROLLMENT, \
 QUERY_TYPE_ENROLLMENT_GROUP, \
 QUERY_TYPE_DEVICE_REGISTRATION_STATE 

```

## Enumeration types

#### PROVISIONING_QUERY_TYPE

```C
enum PROVISIONING_QUERY_TYPE {
  QUERY_TYPE_INVALID,
  QUERY_TYPE_INDIVIDUAL_ENROLLMENT,
  QUERY_TYPE_ENROLLMENT_GROUP,
  QUERY_TYPE_DEVICE_REGISTRATION_STATE
}

```
Constant                    | Description                                
----------------------------|----------------
 QUERY_TYPE_INVALID            | 
 QUERY_TYPE_INDIVIDUAL_ENROLLMENT            | 
 QUERY_TYPE_ENROLLMENT_GROUP            | 
 QUERY_TYPE_DEVICE_REGISTRATION_STATE            | 

