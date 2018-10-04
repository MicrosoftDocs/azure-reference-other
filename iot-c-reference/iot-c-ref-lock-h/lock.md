# Lock()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/lock.h"](../iot-c-ref-lock-h.md)  

[`LOCK_RESULT`](#lock_8h_1a0c50183ac9ba70b668f85ba07a52269c) `[`Lock`](#lock_8h_1a146c21d68c41777d20ef1f7e30518505)(`[`LOCK_HANDLE`](#lock_8h_1a83187a1340d2a8c817783e74f55d8281) handle)`

Acquires a lock on the given lock handle. Uses platform specific mutex primitives in its implementation.

#### Parameters
* `handle` A valid handle to the lock.

#### Returns
Returns `LOCK_OK` when a lock has been acquired and `LOCK_ERROR` when an error occurs.

