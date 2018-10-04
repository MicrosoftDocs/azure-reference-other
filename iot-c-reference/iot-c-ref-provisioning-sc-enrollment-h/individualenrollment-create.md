# individualEnrollment_create()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_enrollment.h"](../iot-c-ref-provisioning-sc-enrollment-h.md)  

## Syntax

```C
INDIVIDUAL_ENROLLMENT_HANDLE individualEnrollment_create(
  const char *                  reg_id,
  ATTESTATION_MECHANISM_HANDLE  att_mech
);

```

Creates an Individual Enrollment handle with a TPM Attestation for use in consequent APIs.

#### Parameters
* `reg_id` A registration id for the Individual Enrollment. 

* `att_mech` The handle for the Attestation Mechanism to be used by the Individual Enrollment

#### Returns
A non-NULL handle representing an Individual Enrollment for use with the Provisioning Service, and NULL on failure.

