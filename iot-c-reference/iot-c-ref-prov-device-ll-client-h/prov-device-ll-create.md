# Prov_Device_LL_Create()

\#include ["azure-iot-sdk-c/provisioning_client/inc/azure_prov_client/prov_device_ll_client.h"](../iot-c-ref-prov-device-ll-client-h.md)  

## Syntax

```C
PROV_DEVICE_LL_HANDLE Prov_Device_LL_Create(
  const char *                             	uri,
  const char *                             	scope_id,
  PROV_DEVICE_TRANSPORT_PROVIDER_FUNCTION  	protocol
);

```

Creates a Provisioning Client for communications with the Device Provisioning Client Service.

#### Parameters
* `uri` The URI of the Device Provisioning Service 

* `scope_id` The customer specific Id Scope 

* `protocol` Function pointer for protocol implementation

#### Returns
A non-NULL PROV_DEVICE_LL_HANDLE value that is used when invoking other functions and NULL on Failure

