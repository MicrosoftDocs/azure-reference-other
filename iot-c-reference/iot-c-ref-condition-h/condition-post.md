# Condition_Post()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/condition.h"](../iot-c-ref-condition-h.md)  

[`COND_RESULT`](#condition_8h_1a806f1a0c35e9db64f4ac300117cc5b15) `[`Condition_Post`](#condition_8h_1a6c9c0376a55779236eee84734666bfb0)(`[`COND_HANDLE`](#condition_8h_1a46761561ff568b25f13484ac4dacefc1) handle)`

unblock all currently working condition.

#### Parameters
* `handle` A valid handle to the lock.

#### Returns
Returns `COND_OK` when the condition object has been destroyed and `COND_ERROR` when an error occurs and `COND_TIMEOUT` when the handle times out.

