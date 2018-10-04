# attestationMechanism_createWithTpm()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_attestation_mechanism.h"](../iot-c-ref-provisioning-sc-attestation-mechanism-h.md)  

[`ATTESTATION_MECHANISM_HANDLE`](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) `[`attestationMechanism_createWithTpm`](#provisioning__sc__attestation__mechanism_8h_1a5682a29373165a4e86e7bdbfd6147814)(const char * endorsement_key,const char * storage_root_key)`

Creates an Attestation Mechanism handle that uses a TPM Attestation for use in consequent APIs.

#### Parameters
* `endorsement_key` An endorsement key to use with the TPM. 

* `storage_root_key` A storage root key to use with the TPM (optional).

#### Returns
A non NULL handle representing an Attestation Mechanism using a TPM Attestation, and NULL on failure.

