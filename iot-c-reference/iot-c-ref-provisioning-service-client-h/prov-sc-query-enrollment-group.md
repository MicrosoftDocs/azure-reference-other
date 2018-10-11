# prov_sc_query_enrollment_group()

Queries enrollment group records from the Provisioning Service.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h](../iot-c-ref-provisioning-service-client-h.md)"  
```C
int prov_sc_query_enrollment_group(
  PROVISIONING_SERVICE_CLIENT_HANDLE  prov_client,
  PROVISIONING_QUERY_SPECIFICATION    query_spec,
  char **                             cont_token_ptr,
  PROVISIONING_QUERY_RESPONSE         query_resp_ptr
);
```

## Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `query_spec` The query specification with query details and settings 

* `cont_token_ptr` A pointer to a continuation token, which will be updated based on the response 

* `query_resp_ptr` A pointer to a query response pointer, which will be filled with retrieved data

## Return Value
0 upon success, a non-zero number upon failure

