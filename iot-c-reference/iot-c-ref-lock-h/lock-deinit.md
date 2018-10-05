# Lock_Deinit()

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/lock.h](../iot-c-ref-lock-h.md)"  

## Syntax

```C
LOCK_RESULT Lock_Deinit(
  LOCK_HANDLE  handle
);
```

The lock instance is destroyed.

## Parameters
* **:handle** A valid handle to the lock.

## Returns
Returns `LOCK_OK` when the lock object has been destroyed and `LOCK_ERROR` when an error occurs.

