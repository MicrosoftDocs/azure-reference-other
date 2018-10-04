# enrollmentGroup_destroy()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_enrollment.h"](../iot-c-ref-provisioning-sc-enrollment-h.md)  

void `[`enrollmentGroup_destroy`](#provisioning__sc__enrollment_8h_1a6531ce2323081afbcfceaa1d1c0db74c)(`[`ENROLLMENT_GROUP_HANDLE`](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment)`

Destorys an Enrollment Group handle, freeing all associated memory. Please note that this also includes the attestation mechanism that was given in the constructor.

#### Parameters
* `enrollment` A handle for the Enrollment Group to be destroyed.

