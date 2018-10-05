# prov_sc_delete_enrollment_group()

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h](../iot-c-ref-provisioning-service-client-h.md)"  

## Syntax

```C
int prov_sc_delete_enrollment_group(
  PROVISIONING_SERVICE_CLIENT_HANDLE  prov_client,

  ENROLLMENT_GROUP_HANDLE             enrollment
);
```

Deletes a device enrollment group record on the Provisioning Service.

## Parameters
* **:prov_client** The handle used for connecting to the Provisioning Service. 

* **:enrollment** The handle for the target enrollment group

## Returns
0 upon success, a non-zero number upon failure.

