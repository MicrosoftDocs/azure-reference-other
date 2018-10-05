# attestationMechanism_createWithX509CAReference()

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_attestation_mechanism.h](../iot-c-ref-provisioning-sc-attestation-mechanism-h.md)"  

## Syntax

```C
ATTESTATION_MECHANISM_HANDLE attestationMechanism_createWithX509CAReference(
  const char *  primary_ref,

  const char *  secondary_ref
);
```

Creates an Attestation Mechanism handle that uses an x509 Attestation with CA Certificate Reference(s) for use in consequent APIs. Please note that an x509 Attestation with a CA Certificate Reference is NOT VALID when attached to an Individual Enrollment.

## Parameters
* **:primary_ref** A reference to a primary CA Certificate for use with the x509. 

* **:secondary_ref** A reference to a secondary CA Certificate for use with the x509 (optional - if not using two cert refs, pass NULL).

## Returns
A non NULL handle representing an Attestation Mechanism using an X509 Attestation with a CA Reference, and NULL on failure.

