# prov_sc_set_proxy()

Set the proxy options for HTTP communication with the Provisioning Service.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h](../iot-c-ref-provisioning-service-client-h.md)"  
```C
int prov_sc_set_proxy(
  PROVISIONING_SERVICE_CLIENT_HANDLE  prov_client,
  HTTP_PROXY_OPTIONS                  proxy_options
);
```

## Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `proxy_options` A struct containing the desired proxy settings

## Returns
0 upon success, a non-zero number upon failure.

