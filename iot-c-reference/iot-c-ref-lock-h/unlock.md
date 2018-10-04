# Unlock()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/lock.h"](../iot-c-ref-lock-h.md)  

[`LOCK_RESULT`](#lock_8h_1a0c50183ac9ba70b668f85ba07a52269c) `[`Unlock`](#lock_8h_1aef3dd970e9edfc49b414aa6cb0f3ad84)(`[`LOCK_HANDLE`](#lock_8h_1a83187a1340d2a8c817783e74f55d8281) handle)`

Releases the lock on the given lock handle. Uses platform specific mutex primitives in its implementation.

#### Parameters
* `handle` A valid handle to the lock.

#### Returns
Returns `LOCK_OK` when the lock has been released and `LOCK_ERROR` when an error occurs.

