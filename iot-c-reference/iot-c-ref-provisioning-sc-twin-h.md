# Header file provisioning_sc_twin.h 

Stub comment for brief. Please update this comment.

## Includes

\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
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

Typedef                        | Value                                
--------------------------------|---------------------------------------------
INITIAL_TWIN_HANDLE            | 

## Function documentation

#### initialTwin_create 
[INITIAL_TWIN_HANDLE](#provisioning__sc__twin_8h_1a8230047b4f4613e6691e5a741e65797f) [initialTwin_create](#provisioning__sc__twin_8h_1acd67fdca9ae906efdb7c10c64418ee23)(const char * tags,const char * desired_properties)

#### initialTwin_destroy 
void [initialTwin_destroy](#provisioning__sc__twin_8h_1a3819b321db3a376deb5cc44d99131bec)([INITIAL_TWIN_HANDLE](#provisioning__sc__twin_8h_1a8230047b4f4613e6691e5a741e65797f) twin)

#### initialTwin_getTags 
const char * [initialTwin_getTags](#provisioning__sc__twin_8h_1a1e5aa9d75c89e0ae70f98d6637f794b4)([INITIAL_TWIN_HANDLE](#provisioning__sc__twin_8h_1a8230047b4f4613e6691e5a741e65797f) twin)

#### initialTwin_setTags 
int [initialTwin_setTags](#provisioning__sc__twin_8h_1ac1009bde3a0daaa23d548d532fa57ab8)([INITIAL_TWIN_HANDLE](#provisioning__sc__twin_8h_1a8230047b4f4613e6691e5a741e65797f) twin,const char * tags)

#### initialTwin_getDesiredProperties 
const char * [initialTwin_getDesiredProperties](#provisioning__sc__twin_8h_1a2e7a93304aa4e1bda67e2ca2fbc92d5c)([INITIAL_TWIN_HANDLE](#provisioning__sc__twin_8h_1a8230047b4f4613e6691e5a741e65797f) twin)

#### initialTwin_setDesiredProperties 
int [initialTwin_setDesiredProperties](#provisioning__sc__twin_8h_1afc44cbb67b48302a5c456540a2bd8800)([INITIAL_TWIN_HANDLE](#provisioning__sc__twin_8h_1a8230047b4f4613e6691e5a741e65797f) twin,const char * desiredProperties)

