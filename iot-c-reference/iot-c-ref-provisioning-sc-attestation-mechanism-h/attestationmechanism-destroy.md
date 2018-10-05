# attestationMechanism_destroy()

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_attestation_mechanism.h](../iot-c-ref-provisioning-sc-attestation-mechanism-h.md)"  

## Syntax

```C
void attestationMechanism_destroy(
  ATTESTATION_MECHANISM_HANDLE  att_mech);
```

Destroys an Attestation Mechanism handle, freeing all allocated memory. Please note that this also includes any memory in more specific handles generated from the handle (e.g. TPM_ATTESTATION_HANDLE). Please note further that this will also cause any Enrollment that the Attestation Mechanism has been attached to to have unexpected behvaiours. Do not use this function unless the attestation mechanism is unattached.

## Parameters
* `att_mech`The handle of the Attestation Mechanism

