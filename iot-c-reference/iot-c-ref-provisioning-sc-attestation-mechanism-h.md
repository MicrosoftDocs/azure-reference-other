# provisioning_sc_attestation_mechanism.h 

Stub comment for brief. Please update this comment.

## Includes

\#include <stdbool.h>  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include "[provisioning_sc_tpm_attestation.h](iot-c-ref-provisioning-sc-tpm-attestation-h.md)"  
\#include "[provisioning_sc_x509_attestation.h](iot-c-ref-provisioning-sc-x509-attestation-h.md)"  
\#include "parson.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[ATTESTATION_TYPEStrings](./iot-c-ref-provisioning-sc-attestation-mechanism-h/attestation-typestrings.md)            | 
[ATTESTATION_TYPE_FromString](./iot-c-ref-provisioning-sc-attestation-mechanism-h/attestation-type-fromstring.md)            | 
[attestationMechanism_createWithTpm](./iot-c-ref-provisioning-sc-attestation-mechanism-h/attestationmechanism-createwithtpm.md)            | Creates an Attestation Mechanism handle that uses a TPM Attestation for use in consequent APIs.
[attestationMechanism_createWithX509ClientCert](./iot-c-ref-provisioning-sc-attestation-mechanism-h/attestationmechanism-createwithx509clientcert.md)            | Creates an Attestation Mechanism handle that uses an x509 Attestation with client certificate(s) for use in consequent APIs. Please note that an x509 Attestation with a client certificate is NOT VALID when attached to an enrollment group.
[attestationMechanism_createWithX509SigningCert](./iot-c-ref-provisioning-sc-attestation-mechanism-h/attestationmechanism-createwithx509signingcert.md)            | Creates an Attestation Mechanism handle that uses an x509 Attestation with signing certificate(s) for use in consequent APIs. Please note that an x509 Attestation with a signing certificate is NOT VALID when attached to an individual enrollment.
[attestationMechanism_createWithX509CAReference](./iot-c-ref-provisioning-sc-attestation-mechanism-h/attestationmechanism-createwithx509careference.md)            | Creates an Attestation Mechanism handle that uses an x509 Attestation with CA Certificate Reference(s) for use in consequent APIs. Please note that an x509 Attestation with a CA Certificate Reference is NOT VALID when attached to an Individual Enrollment.
[attestationMechanism_destroy](./iot-c-ref-provisioning-sc-attestation-mechanism-h/attestationmechanism-destroy.md)            | Destroys an Attestation Mechanism handle, freeing all allocated memory. Please note that this also includes any memory in more specific handles generated from the handle (e.g. TPM_ATTESTATION_HANDLE). Please note further that this will also cause any Enrollment that the Attestation Mechanism has been attached to to have unexpected behvaiours. Do not use this function unless the attestation mechanism is unattached.
[attestationMechanism_isValidForIndividualEnrollment](./iot-c-ref-provisioning-sc-attestation-mechanism-h/attestationmechanism-isvalidforindividualenrollment.md)            | Returns result indicating if an attestation mechanism is valid to be attached to an Individual Enrollment.
[attestationMechanism_isValidForEnrollmentGroup](./iot-c-ref-provisioning-sc-attestation-mechanism-h/attestationmechanism-isvalidforenrollmentgroup.md)            | Returns result indicating if an attestation mechanism is valid to be attached to an Enrollment Group.
[attestationMechanism_getType](./iot-c-ref-provisioning-sc-attestation-mechanism-h/attestationmechanism-gettype.md)            | 
[attestationMechanism_getTpmAttestation](./iot-c-ref-provisioning-sc-attestation-mechanism-h/attestationmechanism-gettpmattestation.md)            | 
[attestationMechanism_getX509Attestation](./iot-c-ref-provisioning-sc-attestation-mechanism-h/attestationmechanism-getx509attestation.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
ATTESTATION_TYPE_VALUES            | 

## Typedefs

#### ATTESTATION_MECHANISM_HANDLE

```C
typedef struct ATTESTATION_MECHANISM_TAG * ATTESTATION_MECHANISM_HANDLE;

```

