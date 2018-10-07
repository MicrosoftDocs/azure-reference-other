# iothub_security_factory.h 

Stub comment for brief. Please update this comment.

## Includes

\#include <stddef.h>  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include "azure_c_shared_utility/buffer_.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IOTHUB_SECURITY_TYPEStrings](./iot-c-ref-iothub-security-factory-h/iothub-security-typestrings.md)            | 
[IOTHUB_SECURITY_TYPE_FromString](./iot-c-ref-iothub-security-factory-h/iothub-security-type-fromstring.md)            | 
[iothub_security_init](./iot-c-ref-iothub-security-factory-h/iothub-security-init.md)            | 
[iothub_security_deinit](./iot-c-ref-iothub-security-factory-h/iothub-security-deinit.md)            | 
[iothub_security_interface](./iot-c-ref-iothub-security-factory-h/iothub-security-interface.md)            | 
[iothub_security_type](./iot-c-ref-iothub-security-factory-h/iothub-security-type.md)            | 

## Macro definitions

#### IOTHUB_SECURITY_TYPE_VALUES

```C
#define IOTHUB_SECURITY_TYPE_VALUES \
        IOTHUB_SECURITY_TYPE_UNKNOWN, \
        IOTHUB_SECURITY_TYPE_SAS, \
        IOTHUB_SECURITY_TYPE_X509, \
        IOTHUB_SECURITY_TYPE_HTTP_EDGE, \
        IOTHUB_SECURITY_TYPE_SYMMETRIC_KEY 
```

## Enumeration types

#### IOTHUB_SECURITY_TYPE

```C
enum IOTHUB_SECURITY_TYPE {
  IOTHUB_SECURITY_TYPE_UNKNOWN,
  IOTHUB_SECURITY_TYPE_SAS,
  IOTHUB_SECURITY_TYPE_X509,
  IOTHUB_SECURITY_TYPE_HTTP_EDGE,
  IOTHUB_SECURITY_TYPE_SYMMETRIC_KEY
}
```

