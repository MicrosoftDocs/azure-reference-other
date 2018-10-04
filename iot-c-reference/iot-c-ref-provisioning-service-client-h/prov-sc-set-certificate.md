# prov_sc_set_certificate()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

**int [prov_sc_set_certificate](#provisioning__service__client_8h_1a57eb08d07d4b31285aa22466b8f34039)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,const char * certificate)**

Set the trusted certificate for HTTP communication with the Provisioning Service.

#### Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `certificate` The trusted certificate to be used for HTTP connections. If given as NULL, will clear a previously set certificate.

#### Returns
0 upon success, a non-zero number upon failure.

