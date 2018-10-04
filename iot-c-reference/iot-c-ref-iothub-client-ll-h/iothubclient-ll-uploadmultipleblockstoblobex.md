# IoTHubClient_LL_UploadMultipleBlocksToBlobEx()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h"](../iot-c-ref-iothub-client-ll-h.md)  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClient_LL_UploadMultipleBlocksToBlobEx(
  IOTHUB_CLIENT_LL_HANDLE	iotHubClientHandle,
  const char *	destinationFileName,
  IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK_EX	getDataCallbackEx,
  void *	context
);

```

This API uploads to Azure Storage the content provided block by block by `getDataCallback` under the blob name devicename/.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `destinationFileName` name of the file. 

* `getDataCallbackEx` A callback to be invoked to acquire the file chunks to be uploaded, as well as to indicate the status of the upload of the previous block. 

* `context` Any data provided by the user to serve as context on getDataCallback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

