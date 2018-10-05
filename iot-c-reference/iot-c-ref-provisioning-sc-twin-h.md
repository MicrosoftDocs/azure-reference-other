# provisioning_sc_twin.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include "parson.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[initialTwin_create](./iot-c-ref-provisioning-sc-twin-h/initialtwin-create.md)            | Creates an Initial Twin handle for use in consequent APIs.
[initialTwin_destroy](./iot-c-ref-provisioning-sc-twin-h/initialtwin-destroy.md)            | Destroys an Initial Twin handle, freeing all associated memory. Please note that this will also cause any Enrollment that the Initial Twin has been attached to to have unexpected behvaiours. Do not use this function unless the Initial Twin is unattached.
[initialTwin_getTags](./iot-c-ref-provisioning-sc-twin-h/initialtwin-gettags.md)            | 
[initialTwin_setTags](./iot-c-ref-provisioning-sc-twin-h/initialtwin-settags.md)            | 
[initialTwin_getDesiredProperties](./iot-c-ref-provisioning-sc-twin-h/initialtwin-getdesiredproperties.md)            | 
[initialTwin_setDesiredProperties](./iot-c-ref-provisioning-sc-twin-h/initialtwin-setdesiredproperties.md)            | 

## Typedefs

#### INITIAL_TWIN_HANDLE

```C
typedef struct INITIAL_TWIN_TAG * INITIAL_TWIN_HANDLE;

```

