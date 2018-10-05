# Unlock()

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/lock.h](../iot-c-ref-lock-h.md)"  

## Syntax

```C
LOCK_RESULT Unlock(
  LOCK_HANDLE  handle
);
```

Releases the lock on the given lock handle. Uses platform specific mutex primitives in its implementation.

## Parameters
* **:handle** A valid handle to the lock.

## Returns
Returns `LOCK_OK` when the lock has been released and `LOCK_ERROR` when an error occurs.

