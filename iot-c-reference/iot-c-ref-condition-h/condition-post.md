# Condition_Post()

unblock all currently working condition.

## Syntax

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/condition.h](../iot-c-ref-condition-h.md)"  
```C
COND_RESULT Condition_Post(
  COND_HANDLE  handle
);
```

## Parameters
* `handle` A valid handle to the lock.

## Return Value
Returns `COND_OK` when the condition object has been destroyed and `COND_ERROR` when an error occurs and `COND_TIMEOUT` when the handle times out.

