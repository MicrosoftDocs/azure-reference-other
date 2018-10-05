# provisioning_service_client.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "[azure_c_shared_utility/shared_util_options.h](iot-c-ref-shared-util-options-h.md)"  
\#include "[provisioning_sc_models.h](iot-c-ref-provisioning-sc-models-h.md)"  
\#include "[provisioning_sc_query.h](iot-c-ref-provisioning-sc-query-h.md)"  
\#include "[provisioning_sc_bulk_operation.h](iot-c-ref-provisioning-sc-bulk-operation-h.md)"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[TRACING_STATUSStrings](./iot-c-ref-provisioning-service-client-h/tracing-statusstrings.md)            | 
[TRACING_STATUS_FromString](./iot-c-ref-provisioning-service-client-h/tracing-status-fromstring.md)            | 
[prov_sc_create_from_connection_string](./iot-c-ref-provisioning-service-client-h/prov-sc-create-from-connection-string.md)            | Creates a Provisioning Service Client handle for use in consequent APIs.
[prov_sc_destroy](./iot-c-ref-provisioning-service-client-h/prov-sc-destroy.md)            | Disposes of resources allocated by creating a Provisioning Service Client handle.
[prov_sc_set_trace](./iot-c-ref-provisioning-service-client-h/prov-sc-set-trace.md)            | Sets tracing/logging of http communications on or off.
[prov_sc_set_certificate](./iot-c-ref-provisioning-service-client-h/prov-sc-set-certificate.md)            | Set the trusted certificate for HTTP communication with the Provisioning Service.
[prov_sc_set_proxy](./iot-c-ref-provisioning-service-client-h/prov-sc-set-proxy.md)            | Set the proxy options for HTTP communication with the Provisioning Service.
[prov_sc_create_or_update_individual_enrollment](./iot-c-ref-provisioning-service-client-h/prov-sc-create-or-update-individual-enrollment.md)            | Creates or updates an individual device enrollment record on the Provisioning Service, reflecting the changes in the given struct.
[prov_sc_delete_individual_enrollment](./iot-c-ref-provisioning-service-client-h/prov-sc-delete-individual-enrollment.md)            | Deletes a individual device enrollment record on the Provisioning Service.
[prov_sc_delete_individual_enrollment_by_param](./iot-c-ref-provisioning-service-client-h/prov-sc-delete-individual-enrollment-by-param.md)            | Deletes an individual device enrollment record on the Provisioning Service.
[prov_sc_get_individual_enrollment](./iot-c-ref-provisioning-service-client-h/prov-sc-get-individual-enrollment.md)            | Retreives an individual device enrollment record from the Provisioning Service.
[prov_sc_query_individual_enrollment](./iot-c-ref-provisioning-service-client-h/prov-sc-query-individual-enrollment.md)            | Queries individual device enrollment records from the Provisioning Service.
[prov_sc_run_individual_enrollment_bulk_operation](./iot-c-ref-provisioning-service-client-h/prov-sc-run-individual-enrollment-bulk-operation.md)            | Performs a bulk operation on individual device enrollment records from the provisioning service.
[prov_sc_create_or_update_enrollment_group](./iot-c-ref-provisioning-service-client-h/prov-sc-create-or-update-enrollment-group.md)            | Creates or updates a device enrollment group record on the Provisioning Service.
[prov_sc_delete_enrollment_group](./iot-c-ref-provisioning-service-client-h/prov-sc-delete-enrollment-group.md)            | Deletes a device enrollment group record on the Provisioning Service.
[prov_sc_delete_enrollment_group_by_param](./iot-c-ref-provisioning-service-client-h/prov-sc-delete-enrollment-group-by-param.md)            | Deletes a device enrollment group record on the Provisioning Service.
[prov_sc_get_enrollment_group](./iot-c-ref-provisioning-service-client-h/prov-sc-get-enrollment-group.md)            | Retreives a device enrollment group record from the Provisioning Service.
[prov_sc_query_enrollment_group](./iot-c-ref-provisioning-service-client-h/prov-sc-query-enrollment-group.md)            | Queries enrollment group records from the Provisioning Service.
[prov_sc_delete_device_registration_state](./iot-c-ref-provisioning-service-client-h/prov-sc-delete-device-registration-state.md)            | Deletes a device registration state on the Provisioning Service.
[prov_sc_delete_device_registration_state_by_param](./iot-c-ref-provisioning-service-client-h/prov-sc-delete-device-registration-state-by-param.md)            | Deletes a device registration state on the Provisioning Service.
[prov_sc_get_device_registration_state](./iot-c-ref-provisioning-service-client-h/prov-sc-get-device-registration-state.md)            | Retreives a device registration state from the Provisioning Service.
[prov_sc_query_device_registration_state](./iot-c-ref-provisioning-service-client-h/prov-sc-query-device-registration-state.md)            | Queries device registration state records from the Provisioning Service.

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
TRACING_STATUS_VALUES            | 

## Typedefs

####PROVISIONING_SERVICE_CLIENT_HANDLE
typedef struct PROVISIONING_SERVICE_CLIENT_TAG * PROVISIONING_SERVICE_CLIENT_HANDLE()

Handle to hide struct and use it in consequent APIs.

