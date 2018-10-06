# IoTHubClient_UploadToBlobAsync()

IoTHubClient_UploadToBlobAsync uploads data from memory to a file in Azure Blob Storage.

## Syntax

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client.h](../iot-c-ref-iothub-client-h.md)"  
```C
IOTHUB_CLIENT_RESULT IoTHubClient_UploadToBlobAsync(
  IOTHUB_CLIENT_HANDLE                iotHubClientHandle,
  const char *                        destinationFileName,
  const unsigned char *               source,
  size_t                              size,
  IOTHUB_CLIENT_FILE_UPLOAD_CALLBACK  iotHubClientFileUploadCallback,
  void *                              context
);
```

## Parameters
* `iotHubClientHandle` The handle created by a call to the IoTHubClient_Create function. 

* `destinationFileName` The name of the file to be created in Azure Blob Storage. 

* `source` The source of data. 

* `size` The size of data. 

* `iotHubClientFileUploadCallback` A callback to be invoked when the file upload operation has finished. 

* `context` A user-provided context to be passed to the file upload callback.

## Return Value
IOTHUB_CLIENT_OK upon success or an error code upon failure.

