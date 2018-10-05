# attestationMechanism_createWithTpm()

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_attestation_mechanism.h](../iot-c-ref-provisioning-sc-attestation-mechanism-h.md)"  

## Syntax

```C
ATTESTATION_MECHANISM_HANDLE attestationMechanism_createWithTpm(
  const char *  endorsement_key,
  const char *  storage_root_key);
```

Creates an Attestation Mechanism handle that uses a TPM Attestation for use in consequent APIs.

## Parameters
* `endorsement_key`An endorsement key to use with the TPM. 

* `storage_root_key`A storage root key to use with the TPM (optional).

## Returns
A non NULL handle representing an Attestation Mechanism using a TPM Attestation, and NULL on failure.

