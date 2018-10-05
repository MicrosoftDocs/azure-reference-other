# Condition_Deinit()

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/condition.h](../iot-c-ref-condition-h.md)"  

## Syntax

```C
void Condition_Deinit(
  COND_HANDLE  handle);
```

The condition instance is deinitialized.

## Parameters
* `handle`A valid handle to the condition.

## Returns
Returns `COND_OK` when the condition object has been destroyed and `COND_ERROR` when an error occurs.

