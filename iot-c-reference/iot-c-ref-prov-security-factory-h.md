# prov_security_factory.h 

Stub comment for brief. Please update this comment.

## Includes

\#include <stddef.h>  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "azure_c_shared_utility/macro_utils.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[SECURE_DEVICE_TYPEStrings](./iot-c-ref-prov-security-factory-h/secure-device-typestrings.md)            | 
[SECURE_DEVICE_TYPE_FromString](./iot-c-ref-prov-security-factory-h/secure-device-type-fromstring.md)            | 
[prov_dev_security_init](./iot-c-ref-prov-security-factory-h/prov-dev-security-init.md)            | 
[prov_dev_security_deinit](./iot-c-ref-prov-security-factory-h/prov-dev-security-deinit.md)            | 
[prov_dev_security_get_type](./iot-c-ref-prov-security-factory-h/prov-dev-security-get-type.md)            | 

## Macro definitions

#### SECURE_DEVICE_TYPE_VALUES

```C
#define SECURE_DEVICE_TYPE_VALUES \
        SECURE_DEVICE_TYPE_UNKNOWN, \
        SECURE_DEVICE_TYPE_TPM, \
        SECURE_DEVICE_TYPE_X509, \
        SECURE_DEVICE_TYPE_HTTP_EDGE, \
        SECURE_DEVICE_TYPE_SYMMETRIC_KEY 
```

## Enumeration types

#### SECURE_DEVICE_TYPE

```C
enum SECURE_DEVICE_TYPE {
  SECURE_DEVICE_TYPE_UNKNOWN,
  SECURE_DEVICE_TYPE_TPM,
  SECURE_DEVICE_TYPE_X509,
  SECURE_DEVICE_TYPE_HTTP_EDGE,
  SECURE_DEVICE_TYPE_SYMMETRIC_KEY
}
```
Constant                    | Description                                
----------------------------|----------------
 SECURE_DEVICE_TYPE_UNKNOWN            | 
 SECURE_DEVICE_TYPE_TPM            | 
 SECURE_DEVICE_TYPE_X509            | 
 SECURE_DEVICE_TYPE_HTTP_EDGE            | 
 SECURE_DEVICE_TYPE_SYMMETRIC_KEY            | 

