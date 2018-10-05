# ThreadAPI_Exit()

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/threadapi.h](../iot-c-ref-threadapi-h.md)"  

## Syntax

```C
void ThreadAPI_Exit(
  int  res);
```

This function is called by a thread when the thread exits.

## Parameters
* `res`An integer that represents the exit status of the thread.

This function is called by a thread when the thread exits in order to return a result value to the caller of the [ThreadAPI_Join](#threadapi_8h_1aa80bce4748cbe10f4b726f2ea3168609) function. The `res` value must be copied into the `res` out argument passed to the [ThreadAPI_Join](#threadapi_8h_1aa80bce4748cbe10f4b726f2ea3168609) function.

