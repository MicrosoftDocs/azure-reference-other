# prov_sc_get_enrollment_group()

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h](../iot-c-ref-provisioning-service-client-h.md)"  

## Syntax

```C
int prov_sc_get_enrollment_group(
  PROVISIONING_SERVICE_CLIENT_HANDLE  prov_client,

  const char *                        group_id,

  ENROLLMENT_GROUP_HANDLE             enrollment_ptr
);
```

Retreives a device enrollment group record from the Provisioning Service.

## Parameters
* **:prov_client** The handle used for connecting to the Provisioning Service. 

* **:group_id** The enrollment group id of the target enrollment group. 

* **:enrollment_ptr** A pointer to a handle for an enrollment group, to be filled with the retreived data.

## Returns
0 upon success, a non-zero number upon failure.

