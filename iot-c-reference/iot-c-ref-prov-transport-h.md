# prov_transport.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include "[azure_c_shared_utility/shared_util_options.h](iot-c-ref-shared-util-options-h.md)"  
\#include "azure_c_shared_utility/buffer_.h"  
\#include <stdbool.h>  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[TRANSPORT_HSM_TYPEStrings](./iot-c-ref-prov-transport-h/transport-hsm-typestrings.md)            | 
[TRANSPORT_HSM_TYPE_FromString](./iot-c-ref-prov-transport-h/transport-hsm-type-fromstring.md)            | 
[PROV_DEVICE_TRANSPORT_RESULTStrings](./iot-c-ref-prov-transport-h/prov-device-transport-resultstrings.md)            | 
[PROV_DEVICE_TRANSPORT_RESULT_FromString](./iot-c-ref-prov-transport-h/prov-device-transport-result-fromstring.md)            | 

## Macro definitions

#### TRANSPORT_HSM_TYPE_VALUES

```C
#define TRANSPORT_HSM_TYPE_VALUES \
 TRANSPORT_HSM_TYPE_TPM, \
 TRANSPORT_HSM_TYPE_X509, \
 TRANSPORT_HSM_TYPE_SYMM_KEY 

```

#### PROV_DEVICE_TRANSPORT_RESULT_VALUES

```C
#define PROV_DEVICE_TRANSPORT_RESULT_VALUES \
 PROV_DEVICE_TRANSPORT_RESULT_OK, \
 PROV_DEVICE_TRANSPORT_RESULT_UNAUTHORIZED, \
 PROV_DEVICE_TRANSPORT_RESULT_ERROR 

```

## Enumeration types

#### TRANSPORT_HSM_TYPE

```C
enum TRANSPORT_HSM_TYPE {
  TRANSPORT_HSM_TYPE_TPM,
  TRANSPORT_HSM_TYPE_X509,
  TRANSPORT_HSM_TYPE_SYMM_KEY
}

```
Constant                    | Description                                
----------------------------|----------------
 TRANSPORT_HSM_TYPE_TPM            | 
 TRANSPORT_HSM_TYPE_X509            | 
 TRANSPORT_HSM_TYPE_SYMM_KEY            | 

#### PROV_DEVICE_TRANSPORT_RESULT

```C
enum PROV_DEVICE_TRANSPORT_RESULT {
  PROV_DEVICE_TRANSPORT_RESULT_OK,
  PROV_DEVICE_TRANSPORT_RESULT_UNAUTHORIZED,
  PROV_DEVICE_TRANSPORT_RESULT_ERROR
}

```
Constant                    | Description                                
----------------------------|----------------
 PROV_DEVICE_TRANSPORT_RESULT_OK            | 
 PROV_DEVICE_TRANSPORT_RESULT_UNAUTHORIZED            | 
 PROV_DEVICE_TRANSPORT_RESULT_ERROR            | 

## Typedef documentation

#### PROV_DEVICE_TRANSPORT_PROVIDER

```C
typedef struct PROV_DEVICE_TRANSPORT_PROVIDER_TAG PROV_DEVICE_TRANSPORT_PROVIDER;
```

#### PROV_DEVICE_TRANSPORT_HANDLE

```C
typedef void* PROV_DEVICE_TRANSPORT_HANDLE;
```

