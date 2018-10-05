# enrollmentGroup_create()

Creates an Enrollment Group handle with an X509 Attestation for use in consequent APIs.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_enrollment.h](../iot-c-ref-provisioning-sc-enrollment-h.md)"  
```C
ENROLLMENT_GROUP_HANDLE enrollmentGroup_create(
  const char *                  group_id,
  ATTESTATION_MECHANISM_HANDLE  att_mech
);
```

## Parameters
* `group_id` A group name for the Enrollment Group. 

* `att_mech` The handle for the Attestation Mechanism to be used by the Enrollment Group. Note: only valid with type: X509

## Returns
A non-NULL handle representing an Enrollment Group for use with the Provisioning Service, and NULL on failure.

