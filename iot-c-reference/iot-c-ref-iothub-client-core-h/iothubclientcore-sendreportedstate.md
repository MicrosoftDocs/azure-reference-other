# IoTHubClientCore_SendReportedState()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client_core.h"](../iot-c-ref-iothub-client-core-h.md)  

## Syntax

```C
IOTHUB_CLIENT_RESULT IoTHubClientCore_SendReportedState(
  IOTHUB_CLIENT_CORE_HANDLE	iotHubClientHandle,
  const unsigned char *	reportedState,
  size_t	size,
  IOTHUB_CLIENT_REPORTED_STATE_CALLBACK	reportedStateCallback,
  void *	userContextCallback
);

```

