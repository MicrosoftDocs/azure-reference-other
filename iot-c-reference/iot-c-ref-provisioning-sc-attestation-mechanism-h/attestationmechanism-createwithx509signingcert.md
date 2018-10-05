# attestationMechanism_createWithX509SigningCert()

Creates an Attestation Mechanism handle that uses an x509 Attestation with signing certificate(s) for use in consequent APIs. Please note that an x509 Attestation with a signing certificate is NOT VALID when attached to an individual enrollment.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_attestation_mechanism.h](../iot-c-ref-provisioning-sc-attestation-mechanism-h.md)"  
```C
ATTESTATION_MECHANISM_HANDLE attestationMechanism_createWithX509SigningCert(
  const char *  primary_cert,
  const char *  secondary_cert
);
```

## Parameters
* `primary_cert` A primary certificate for use with the x509. 

* `secondary_cert` A secondary certificate for use with the x509 (optional - if not using two certs, pass NULL).

## Returns
A non NULL handle representing an Attestation Mechanism using an X509 Attestation with a signing certificate, and NULL on failure.

