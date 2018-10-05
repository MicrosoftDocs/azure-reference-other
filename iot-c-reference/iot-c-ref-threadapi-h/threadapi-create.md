# ThreadAPI_Create()

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/threadapi.h](../iot-c-ref-threadapi-h.md)"  

## Syntax

```C
THREADAPI_RESULT ThreadAPI_Create(
  THREAD_HANDLE      threadHandle,
  THREAD_START_FUNC  func,
  void *             arg
);
```

Creates a thread with the entry point specified by the `func` argument.

## Parameters
* `threadHandle`The handle to the new thread is returned in this pointer. 

* `func`A function pointer that indicates the entry point to the new thread. 

* `arg`A void pointer that must be passed to the function pointed to by `func`.

## Returns
`THREADAPI_OK` if the API call is successful or an error code in case it fails.

