# Condition_Wait()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/condition.h"](../iot-c-ref-condition-h.md)  

**[COND_RESULT](#condition_8h_1a806f1a0c35e9db64f4ac300117cc5b15) [Condition_Wait](#condition_8h_1a4b4991898d5ef09be8deeabef9d94f54)([COND_HANDLE](#condition_8h_1a46761561ff568b25f13484ac4dacefc1) handle,[LOCK_HANDLE](#lock_8h_1a83187a1340d2a8c817783e74f55d8281) lock,int timeout_milliseconds)**

block on the condition handle unti the thread is signalled or until the timeout_milliseconds is reached.

#### Parameters
* `handle` A valid handle to the lock.

#### Returns
Returns `COND_OK` when the condition object has been destroyed and `COND_ERROR` when an error occurs and `COND_TIMEOUT` when the handle times out.

