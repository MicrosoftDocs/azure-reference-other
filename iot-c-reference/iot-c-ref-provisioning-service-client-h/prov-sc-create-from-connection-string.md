# prov_sc_create_from_connection_string()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

## Syntax

```C
PROVISIONING_SERVICE_CLIENT_HANDLE prov_sc_create_from_connection_string(
  const char *  conn_string
);

```

Creates a Provisioning Service Client handle for use in consequent APIs.

#### Parameters
* `conn_string` A connection string used to establish connection with the Provisioning Service.

#### Returns
A non-NULL PROVISIONING_SERVICE_CLIENT_HANDLE value that is used when invoking other functions in the Provisioning Service Client and NULL on failure.

