# IoTHubMessaging_LL_SetTrustedCert()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging_ll.h"](../iot-c-ref-iothub-messaging-ll-h.md)  

## Syntax

```C
IOTHUB_MESSAGING_RESULT IoTHubMessaging_LL_SetTrustedCert(
  IOTHUB_MESSAGING_HANDLE  	messagingHandle,
  const char *             	trusted_cert
);

```

This function is meant to be called by the user when to set the trusted certificate on the tls connection.

#### Parameters
* `messagingHandle` The handle created by a call to the create function. 

* `trusted_cert` The trusted certificate that will be set.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

