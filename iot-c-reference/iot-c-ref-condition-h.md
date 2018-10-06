# condition.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include "[azure_c_shared_utility/lock.h](iot-c-ref-lock-h.md)"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[COND_RESULTStrings](./iot-c-ref-condition-h/cond-resultstrings.md)            | 
[COND_RESULT_FromString](./iot-c-ref-condition-h/cond-result-fromstring.md)            | 
[Condition_Init](./iot-c-ref-condition-h/condition-init.md)            | This API creates and returns a valid condition handle.
[Condition_Post](./iot-c-ref-condition-h/condition-post.md)            | unblock all currently working condition.
[Condition_Wait](./iot-c-ref-condition-h/condition-wait.md)            | block on the condition handle unti the thread is signalled or until the timeout_milliseconds is reached.
[Condition_Deinit](./iot-c-ref-condition-h/condition-deinit.md)            | The condition instance is deinitialized.

## Macro definitions

#### COND_RESULT_VALUES

```C
#define COND_RESULT_VALUES \
 COND_OK, \
 COND_INVALID_ARG, \
 COND_ERROR, \
 COND_TIMEOUT 

```

## Enumeration types

#### COND_RESULT

Enumeration specifying the lock status. 

```C
enum COND_RESULT {
  COND_OK,
  COND_INVALID_ARG,
  COND_ERROR,
  COND_TIMEOUT
}

```
Constant                    | Description                                
----------------------------|----------------
 COND_OK            | 
 COND_INVALID_ARG            | 
 COND_ERROR            | 
 COND_TIMEOUT            | 

