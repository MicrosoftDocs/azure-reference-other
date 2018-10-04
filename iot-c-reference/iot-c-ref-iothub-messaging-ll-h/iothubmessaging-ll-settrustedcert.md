# IoTHubMessaging_LL_SetTrustedCert()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_messaging_ll.h"](../iot-c-ref-iothub-messaging-ll-h.md)  

**[IOTHUB_MESSAGING_RESULT](#iothub__messaging__ll_8h_1ac5ac4fdc87db94cc7ddb7773e79290cd) [IoTHubMessaging_LL_SetTrustedCert](#iothub__messaging__ll_8h_1a137346dac27148c3055f798b3be72cf2)([IOTHUB_MESSAGING_HANDLE](#iothub__messaging__ll_8h_1ad4dd5cf65fd836ab5b053d59148343ff) messagingHandle,const char * trusted_cert)**

This function is meant to be called by the user when to set the trusted certificate on the tls connection.

#### Parameters
* `messagingHandle` The handle created by a call to the create function. 

* `trusted_cert` The trusted certificate that will be set.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

