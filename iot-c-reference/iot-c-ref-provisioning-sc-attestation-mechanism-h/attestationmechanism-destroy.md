# attestationMechanism_destroy()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_attestation_mechanism.h"](../iot-c-ref-provisioning-sc-attestation-mechanism-h.md)  

void `[`attestationMechanism_destroy`](#provisioning__sc__attestation__mechanism_8h_1ad66814a3291e09796ab0a68a46f6ecc4)(`[`ATTESTATION_MECHANISM_HANDLE`](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) att_mech)`

Destroys an Attestation Mechanism handle, freeing all allocated memory. Please note that this also includes any memory in more specific handles generated from the handle (e.g. TPM_ATTESTATION_HANDLE). Please note further that this will also cause any Enrollment that the Attestation Mechanism has been attached to to have unexpected behvaiours. Do not use this function unless the attestation mechanism is unattached.

#### Parameters
* `att_mech` The handle of the Attestation Mechanism

