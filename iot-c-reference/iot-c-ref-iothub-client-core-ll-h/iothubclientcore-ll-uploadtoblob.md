# IoTHubClientCore_LL_UploadToBlob()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_client_core_ll.h](../iot-c-ref-iothub-client-core-ll-h.md)"  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClientCore_LL_UploadToBlob(
  IOTHUB_CLIENT_CORE_LL_HANDLE  iotHubClientHandle,

  const char *                  destinationFileName,

  const unsigned char *         source,

  size_t                        size
);
```

