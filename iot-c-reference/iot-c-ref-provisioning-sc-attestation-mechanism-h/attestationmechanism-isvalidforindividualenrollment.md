# attestationMechanism_isValidForIndividualEnrollment()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_attestation_mechanism.h"](../iot-c-ref-provisioning-sc-attestation-mechanism-h.md)  

## Syntax

```C
bool attestationMechanism_isValidForIndividualEnrollment(
  ATTESTATION_MECHANISM_HANDLE	att_mech
);

```

Returns result indicating if an attestation mechanism is valid to be attached to an Individual Enrollment.

#### Parameters
* `att_mech` The handle of the Attestation Mechanism

