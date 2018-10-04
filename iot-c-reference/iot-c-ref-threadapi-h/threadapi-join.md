# ThreadAPI_Join()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/threadapi.h"](../iot-c-ref-threadapi-h.md)  

[`THREADAPI_RESULT`](#threadapi_8h_1a040c14bc535115c79e2f9daa57d268bd) `[`ThreadAPI_Join`](#threadapi_8h_1aa80bce4748cbe10f4b726f2ea3168609)(`[`THREAD_HANDLE`](#threadapi_8h_1a51f9e04bbea1ebd9fd7281a2f2a4fbf3) threadHandle,int * res)`

Blocks the calling thread by waiting on the thread identified by the `threadHandle` argument to complete.

#### Parameters
* `threadHandle` The handle of the thread to wait for completion. 

* `res` The result returned by the thread which is passed to the [ThreadAPI_Exit](#threadapi_8h_1a304fd6867f922d6321f36569d1769d04) function.

When the `threadHandle` thread completes, all resources associated with the thread must be released and the thread handle will no longer be valid.

#### Returns
`THREADAPI_OK` if the API call is successful or an error code in case it fails.

