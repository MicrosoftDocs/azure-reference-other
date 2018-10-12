# prov_sc_destroy()

Disposes of resources allocated by creating a Provisioning Service Client handle.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h](../iot-c-ref-provisioning-service-client-h.md)"  
```C
void prov_sc_destroy(
  PROVISIONING_SERVICE_CLIENT_HANDLE  prov_client
);
```

## Parameters
* `prov_client` The handle created by a call to the create function.

