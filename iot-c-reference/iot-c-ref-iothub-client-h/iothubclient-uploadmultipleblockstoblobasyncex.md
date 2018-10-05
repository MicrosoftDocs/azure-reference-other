# IoTHubClient_UploadMultipleBlocksToBlobAsyncEx()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client.h](../iot-c-ref-iothub-client-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClient_UploadMultipleBlocksToBlobAsyncEx(
  IOTHUB_CLIENT_HANDLE                            iotHubClientHandle,

  const char *                                    destinationFileName,

  IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK_EX  getDataCallbackEx,

  void *                                          context
);
```

Uploads a file to a Blob storage in chunks, fed through the callback function provided by the user.

This function allows users to upload large files in chunks, not requiring the whole file content to be passed in memory. 

## Parameters
* **:iotHubClientHandle** The handle created by a call to the IoTHubClient_Create function. 

* **:destinationFileName** The name of the file to be created in Azure Blob Storage. 

* **:getDataCallbackEx** A callback to be invoked to acquire the file chunks to be uploaded, as well as to indicate the status of the upload of the previous block. 

* **:context** Any data provided by the user to serve as context on getDataCallback. 

## Returns
An IOTHUB_CLIENT_RESULT value indicating the success or failure of the API call.

