# IoTHubMessaging_SetTrustedCert()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging.h"](../iot-c-ref-iothub-messaging-h.md)  

[`IOTHUB_MESSAGING_RESULT`](#iothub__messaging__ll_8h_1ac5ac4fdc87db94cc7ddb7773e79290cd) `[`IoTHubMessaging_SetTrustedCert`](#iothub__messaging_8h_1ae097c37e0046bb193c1e14dd8c8434be)(`[`IOTHUB_MESSAGING_CLIENT_HANDLE`](#iothub__messaging_8h_1a388e756ded834589f37bbd04bf9cc9c0) messagingClientHandle,const char * trusted_cert)`

This function is meant to be called by the user when to set the trusted certificate on the tls connection.

#### Parameters
* `messagingHandle` The handle created by a call to the create function. 

* `trusted_cert` The trusted certificate that will be set.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

