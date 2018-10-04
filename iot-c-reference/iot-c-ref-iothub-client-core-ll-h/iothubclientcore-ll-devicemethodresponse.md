# IoTHubClientCore_LL_DeviceMethodResponse()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client_core_ll.h"](../iot-c-ref-iothub-client-core-ll-h.md)  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClientCore_LL_DeviceMethodResponse(
  IOTHUB_CLIENT_CORE_LL_HANDLE	iotHubClientHandle,
  METHOD_HANDLE	methodId,
  const unsigned char *	response,
  size_t	respSize,
  int	statusCode
);

```

