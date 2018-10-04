# enrollmentGroup_create()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_enrollment.h"](../iot-c-ref-provisioning-sc-enrollment-h.md)  

[`ENROLLMENT_GROUP_HANDLE`](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) `[`enrollmentGroup_create`](#provisioning__sc__enrollment_8h_1a67af9532e246f745aa12f07093f99c31)(const char * group_id,`[`ATTESTATION_MECHANISM_HANDLE`](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) att_mech)`

Creates an Enrollment Group handle with an X509 Attestation for use in consequent APIs.

#### Parameters
* `group_id` A group name for the Enrollment Group. 

* `att_mech` The handle for the Attestation Mechanism to be used by the Enrollment Group. Note: only valid with type: X509

#### Returns
A non-NULL handle representing an Enrollment Group for use with the Provisioning Service, and NULL on failure.

