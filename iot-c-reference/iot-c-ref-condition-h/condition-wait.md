# Condition_Wait()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/condition.h"](../iot-c-ref-condition-h.md)  

## Syntax

```C
COND_RESULT Condition_Wait(
  COND_HANDLE  	handle,
  LOCK_HANDLE  	lock,
  int          	timeout_milliseconds
);

```

block on the condition handle unti the thread is signalled or until the timeout_milliseconds is reached.

#### Parameters
* `handle` A valid handle to the lock.

#### Returns
Returns `COND_OK` when the condition object has been destroyed and `COND_ERROR` when an error occurs and `COND_TIMEOUT` when the handle times out.

