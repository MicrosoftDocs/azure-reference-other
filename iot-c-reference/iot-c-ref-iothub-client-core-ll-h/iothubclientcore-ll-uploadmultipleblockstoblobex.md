# IoTHubClientCore_LL_UploadMultipleBlocksToBlobEx()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client_core_ll.h"](../iot-c-ref-iothub-client-core-ll-h.md)  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClientCore_LL_UploadMultipleBlocksToBlobEx(
  IOTHUB_CLIENT_CORE_LL_HANDLE                    	iotHubClientHandle,
  const char *                                    	destinationFileName,
  IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK_EX  	getDataCallbackEx,
  void *                                          	context
);

```

