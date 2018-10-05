# IoTHubClientCore_UploadToBlobAsync()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_core.h](../iot-c-ref-iothub-client-core-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClientCore_UploadToBlobAsync(
  IOTHUB_CLIENT_CORE_HANDLE           iotHubClientHandle,
  const char *                        destinationFileName,
  const unsigned char *               source,
  size_t                              size,
  IOTHUB_CLIENT_FILE_UPLOAD_CALLBACK  iotHubClientFileUploadCallback,
  void *                              context);
```

