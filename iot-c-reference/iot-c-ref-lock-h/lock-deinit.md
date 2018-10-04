# Lock_Deinit()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/lock.h"](../iot-c-ref-lock-h.md)  

[`LOCK_RESULT`](#lock_8h_1a0c50183ac9ba70b668f85ba07a52269c) `[`Lock_Deinit`](#lock_8h_1ac9743d97f19aac4a0bda808e57ef1249)(`[`LOCK_HANDLE`](#lock_8h_1a83187a1340d2a8c817783e74f55d8281) handle)`

The lock instance is destroyed.

#### Parameters
* `handle` A valid handle to the lock.

#### Returns
Returns `LOCK_OK` when the lock object has been destroyed and `LOCK_ERROR` when an error occurs.

