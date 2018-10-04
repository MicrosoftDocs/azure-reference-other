# Header file condition.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_c_shared_utility/lock.h"](iot-c-ref-lock-h.md)  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  

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

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
COND_RESULT_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
COND_HANDLE            | 

## Function documentation

#### COND_RESULTStrings 
const char * [COND_RESULTStrings](#condition_8h_1a1b6608dee573eece9e42ea1a9c53e8cf)([COND_RESULT](#condition_8h_1a806f1a0c35e9db64f4ac300117cc5b15) value)

#### COND_RESULT_FromString 
int [COND_RESULT_FromString](#condition_8h_1a4981adb26d3372ea7b5957bbd654e68e)(const char * enumAsString,[COND_RESULT](#condition_8h_1a806f1a0c35e9db64f4ac300117cc5b15) * destination)

#### Condition_Init 
[COND_HANDLE](#condition_8h_1a46761561ff568b25f13484ac4dacefc1) [Condition_Init](#condition_8h_1a7ad28345ff884d9743b00c6ffbfd3568)(void)

#### Condition_Post 
[COND_RESULT](#condition_8h_1a806f1a0c35e9db64f4ac300117cc5b15) [Condition_Post](#condition_8h_1a6c9c0376a55779236eee84734666bfb0)([COND_HANDLE](#condition_8h_1a46761561ff568b25f13484ac4dacefc1) handle)

#### Condition_Wait 
[COND_RESULT](#condition_8h_1a806f1a0c35e9db64f4ac300117cc5b15) [Condition_Wait](#condition_8h_1a4b4991898d5ef09be8deeabef9d94f54)([COND_HANDLE](#condition_8h_1a46761561ff568b25f13484ac4dacefc1) handle,[LOCK_HANDLE](#lock_8h_1a83187a1340d2a8c817783e74f55d8281) lock,int timeout_milliseconds)

#### Condition_Deinit 
void [Condition_Deinit](#condition_8h_1a38d88f96ffcdf8ad01bed9a401f64d94)([COND_HANDLE](#condition_8h_1a46761561ff568b25f13484ac4dacefc1) handle)

