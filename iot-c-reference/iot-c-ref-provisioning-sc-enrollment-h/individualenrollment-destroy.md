# individualEnrollment_destroy()

Destroys an Individual Enrollment handle, freeing all associated memory. Please note that this also includes the attestation mechanism that was given in the constructor.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_enrollment.h](../iot-c-ref-provisioning-sc-enrollment-h.md)"  
```C
void individualEnrollment_destroy(
  INDIVIDUAL_ENROLLMENT_HANDLE  enrollment
);
```

## Parameters
* `enrollment` A handle for the Individual Enrollment to be destroyed.

