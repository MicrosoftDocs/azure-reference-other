# ThreadAPI_Create()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/threadapi.h"](../iot-c-ref-threadapi-h.md)  

**[THREADAPI_RESULT](#threadapi_8h_1a040c14bc535115c79e2f9daa57d268bd) [ThreadAPI_Create](#threadapi_8h_1aed50c815f4090261c06968bb90644b50)([THREAD_HANDLE](#threadapi_8h_1a51f9e04bbea1ebd9fd7281a2f2a4fbf3) * threadHandle,[THREAD_START_FUNC](#threadapi_8h_1a4723071f401ed47e83b73be265a71d4f) func,void * arg)**

Creates a thread with the entry point specified by the `func` argument.

#### Parameters
* `threadHandle` The handle to the new thread is returned in this pointer. 

* `func` A function pointer that indicates the entry point to the new thread. 

* `arg` A void pointer that must be passed to the function pointed to by `func`.

#### Returns
`THREADAPI_OK` if the API call is successful or an error code in case it fails.

