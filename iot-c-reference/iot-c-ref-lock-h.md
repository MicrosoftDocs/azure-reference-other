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

## Function documentation

#### LOCK_RESULTStrings 
const char * `[`LOCK_RESULTStrings`](#lock_8h_1a10329414e53520e4ce34ffd3e0062a83)(`[`LOCK_RESULT`](#lock_8h_1a0c50183ac9ba70b668f85ba07a52269c) value)`

#### LOCK_RESULT_FromString 
int `[`LOCK_RESULT_FromString`](#lock_8h_1aeb20cf6e5a5d068526159dadb6d74e9d)(const char * enumAsString,`[`LOCK_RESULT`](#lock_8h_1a0c50183ac9ba70b668f85ba07a52269c) * destination)`

#### Lock_Init 
[`LOCK_HANDLE`](#lock_8h_1a83187a1340d2a8c817783e74f55d8281) `[`Lock_Init`](#lock_8h_1a3683432285e999baa8c543f27633829c)(void)`

#### Lock 
[`LOCK_RESULT`](#lock_8h_1a0c50183ac9ba70b668f85ba07a52269c) `[`Lock`](#lock_8h_1a146c21d68c41777d20ef1f7e30518505)(`[`LOCK_HANDLE`](#lock_8h_1a83187a1340d2a8c817783e74f55d8281) handle)`

#### Unlock 
[`LOCK_RESULT`](#lock_8h_1a0c50183ac9ba70b668f85ba07a52269c) `[`Unlock`](#lock_8h_1aef3dd970e9edfc49b414aa6cb0f3ad84)(`[`LOCK_HANDLE`](#lock_8h_1a83187a1340d2a8c817783e74f55d8281) handle)`

#### Lock_Deinit 
[`LOCK_RESULT`](#lock_8h_1a0c50183ac9ba70b668f85ba07a52269c) `[`Lock_Deinit`](#lock_8h_1ac9743d97f19aac4a0bda808e57ef1249)(`[`LOCK_HANDLE`](#lock_8h_1a83187a1340d2a8c817783e74f55d8281) handle)`

