# prov_sc_set_certificate()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

## Syntax

```C
int prov_sc_set_certificate(
  PROVISIONING_SERVICE_CLIENT_HANDLE  prov_client,
  const char *                        certificate
);

```

Set the trusted certificate for HTTP communication with the Provisioning Service.

#### Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `certificate` The trusted certificate to be used for HTTP connections. If given as NULL, will clear a previously set certificate.

#### Returns
0 upon success, a non-zero number upon failure.

