# IoTHubClientCore_UploadMultipleBlocksToBlobAsync()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_core.h](../iot-c-ref-iothub-client-core-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClientCore_UploadMultipleBlocksToBlobAsync(
  IOTHUB_CLIENT_CORE_HANDLE                       iotHubClientHandle,

  const char *                                    destinationFileName,

  IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK     getDataCallback,

  IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK_EX  getDataCallbackEx,

  void *                                          context
);
```

