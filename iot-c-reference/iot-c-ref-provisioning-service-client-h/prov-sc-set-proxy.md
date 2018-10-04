# prov_sc_set_proxy()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

## Syntax

```C
int prov_sc_set_proxy(
  PROVISIONING_SERVICE_CLIENT_HANDLE  	prov_client,
  HTTP_PROXY_OPTIONS                  	proxy_options
);

```

Set the proxy options for HTTP communication with the Provisioning Service.

#### Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `proxy_options` A struct containing the desired proxy settings

#### Returns
0 upon success, a non-zero number upon failure.

