# Lock_Deinit()

The lock instance is destroyed.

## Syntax

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/lock.h](../iot-c-ref-lock-h.md)"  
```C
LOCK_RESULT Lock_Deinit(
  LOCK_HANDLE  handle
);
```

## Parameters
* `handle` A valid handle to the lock.

## Returns
Returns `LOCK_OK` when the lock object has been destroyed and `LOCK_ERROR` when an error occurs.

