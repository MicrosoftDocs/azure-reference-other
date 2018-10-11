# prov_sc_run_individual_enrollment_bulk_operation()

Performs a bulk operation on individual device enrollment records from the provisioning service.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h](../iot-c-ref-provisioning-service-client-h.md)"  
```C
int prov_sc_run_individual_enrollment_bulk_operation(
  PROVISIONING_SERVICE_CLIENT_HANDLE  prov_client,
  PROVISIONING_BULK_OPERATION         bulk_op,
  PROVISIONING_BULK_OPERATION_RESULT  bulk_res_ptr
);
```

## Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `bulk_op` A pointer to a bulk operation structure with details about the bulk operation. 

* `bulk_res_ptr` A pointer to a bulk operation result pointer that will be filled with the results upon completion

## Return Value
0 upon success, a non-zero number upon failure.

