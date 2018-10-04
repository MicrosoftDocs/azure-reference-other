# individualEnrollment_destroy()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_enrollment.h"](../iot-c-ref-provisioning-sc-enrollment-h.md)  

void `[`individualEnrollment_destroy`](#provisioning__sc__enrollment_8h_1a8c043d2c029a3bb1ed500dcdb6303c1f)(`[`INDIVIDUAL_ENROLLMENT_HANDLE`](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)`

Destroys an Individual Enrollment handle, freeing all associated memory. Please note that this also includes the attestation mechanism that was given in the constructor.

#### Parameters
* `enrollment` A handle for the Individual Enrollment to be destroyed.

