# individualEnrollment_create()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_enrollment.h"](../iot-c-ref-provisioning-sc-enrollment-h.md)  

[`INDIVIDUAL_ENROLLMENT_HANDLE`](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) `[`individualEnrollment_create`](#provisioning__sc__enrollment_8h_1a070ace8d9abad98df60f17410bc4a945)(const char * reg_id,`[`ATTESTATION_MECHANISM_HANDLE`](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) att_mech)`

Creates an Individual Enrollment handle with a TPM Attestation for use in consequent APIs.

#### Parameters
* `reg_id` A registration id for the Individual Enrollment. 

* `att_mech` The handle for the Attestation Mechanism to be used by the Individual Enrollment

#### Returns
A non-NULL handle representing an Individual Enrollment for use with the Provisioning Service, and NULL on failure.

