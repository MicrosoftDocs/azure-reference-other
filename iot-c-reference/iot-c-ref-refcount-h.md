# refcount.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "[azure_c_shared_utility/gballoc.h](iot-c-ref-gballoc-h.md)"  
\#include <stdlib.h>  
\#include <stdint.h>  
\#include "refcount_os.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Macro definitions

#### REFCOUNT_TYPE

```C
#define REFCOUNT_TYPE  struct C2(C2(REFCOUNT_, type), _TAG) 
```

#### REFCOUNT_SHORT_TYPE

```C
#define REFCOUNT_SHORT_TYPE  C2(REFCOUNT_, type) 
```

#### REFCOUNT_TYPE_DECLARE_CREATE

```C
#define REFCOUNT_TYPE_DECLARE_CREATE        REFCOUNT_SHORT_TYPE 
```

#### REFCOUNT_TYPE_CREATE

```C
#define REFCOUNT_TYPE_CREATE        REFCOUNT_SHORT_TYPE 
```

#### DEFINE_REFCOUNT_TYPE

```C
#define DEFINE_REFCOUNT_TYPE \
        REFCOUNT_TYPE, \
        REFCOUNT_TYPE_DECLARE_CREATE, \
        REFCOUNT_TYPE, \
        REFCOUNT_TYPE, \
        REFCOUNT_TYPE 
```

