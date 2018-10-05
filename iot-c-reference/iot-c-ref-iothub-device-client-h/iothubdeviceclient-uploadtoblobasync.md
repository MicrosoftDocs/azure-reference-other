# IoTHubDeviceClient_UploadToBlobAsync()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h](../iot-c-ref-iothub-device-client-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubDeviceClient_UploadToBlobAsync(
  IOTHUB_DEVICE_CLIENT_HANDLE         iotHubClientHandle,
  const char *                        destinationFileName,
  const unsigned char *               source,
  size_t                              size,
  IOTHUB_CLIENT_FILE_UPLOAD_CALLBACK  iotHubClientFileUploadCallback,
  void *                              context);
```

IoTHubDeviceClient_UploadToBlobAsync uploads data from memory to a file in Azure Blob Storage.

## Parameters
* `iotHubClientHandle`The handle created by a call to the IoTHubDeviceClient_Create function. 

* `destinationFileName`The name of the file to be created in Azure Blob Storage. 

* `source`The source of data. 

* `size`The size of data. 

* `iotHubClientFileUploadCallback`A callback to be invoked when the file upload operation has finished. 

* `context`A user-provided context to be passed to the file upload callback.

## Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

