# ThreadAPI_Exit()

This function is called by a thread when the thread exits.

## Syntax

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/threadapi.h](../iot-c-ref-threadapi-h.md)"  
```C
void ThreadAPI_Exit(
  int  res
);
```

## Parameters
* `res` An integer that represents the exit status of the thread.

This function is called by a thread when the thread exits in order to return a result value to the caller of the [ThreadAPI_Join](../iot-c-ref-threadapi-h/threadapi-join.md) function. The res value must be copied into the res out argument passed to the [ThreadAPI_Join](../iot-c-ref-threadapi-h/threadapi-join.md) function.

