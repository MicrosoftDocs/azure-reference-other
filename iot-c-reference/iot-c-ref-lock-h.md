# Header file lock.h 

A minimalistic platform agnostic lock abstraction for thread synchronization.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  

## Detailed Description

The Lock component is implemented in order to achieve thread synchronization, as we may have a requirement to consume locks across different platforms. This component exposes some generic APIs so that it can be extended for platform specific implementations.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[LOCK_RESULTStrings](./iot-c-ref-lock-h/lock-resultstrings.md)            | 
[LOCK_RESULT_FromString](./iot-c-ref-lock-h/lock-result-fromstring.md)            | 
[Lock_Init](./iot-c-ref-lock-h/lock-init.md)            | This API creates and returns a valid lock handle.
[Lock](./iot-c-ref-lock-h/lock.md)            | Acquires a lock on the given lock handle. Uses platform specific mutex primitives in its implementation.
[Unlock](./iot-c-ref-lock-h/unlock.md)            | Releases the lock on the given lock handle. Uses platform specific mutex primitives in its implementation.
[Lock_Deinit](./iot-c-ref-lock-h/lock-deinit.md)            | The lock instance is destroyed.

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
LOCK_RESULT_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
LOCK_HANDLE            | 

