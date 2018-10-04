# Header file provisioning_sc_attestation_mechanism.h 

Stub comment for brief. Please update this comment.

## Includes

\#include <stdbool.h>  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["provisioning_sc_tpm_attestation.h"](iot-c-ref-provisioning-sc-tpm-attestation-h.md)  
\#include ["provisioning_sc_x509_attestation.h"](iot-c-ref-provisioning-sc-x509-attestation-h.md)  
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

Typedef                        | Value                                
--------------------------------|---------------------------------------------
ATTESTATION_MECHANISM_HANDLE            | 

## Function documentation

#### ATTESTATION_TYPEStrings 
const char * [ATTESTATION_TYPEStrings](#provisioning__sc__attestation__mechanism_8h_1a4ac1fa9314c936ac50c318a612a6c3a8)([ATTESTATION_TYPE](#provisioning__sc__attestation__mechanism_8h_1a48a04269fd3dcfeeb6523c937b3b8760) value)

#### ATTESTATION_TYPE_FromString 
int [ATTESTATION_TYPE_FromString](#provisioning__sc__attestation__mechanism_8h_1a3aaf8340708c8bf58bb7305692a28211)(const char * enumAsString,[ATTESTATION_TYPE](#provisioning__sc__attestation__mechanism_8h_1a48a04269fd3dcfeeb6523c937b3b8760) * destination)

#### attestationMechanism_createWithTpm 
[ATTESTATION_MECHANISM_HANDLE](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) [attestationMechanism_createWithTpm](#provisioning__sc__attestation__mechanism_8h_1a5682a29373165a4e86e7bdbfd6147814)(const char * endorsement_key,const char * storage_root_key)

#### attestationMechanism_createWithX509ClientCert 
[ATTESTATION_MECHANISM_HANDLE](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) [attestationMechanism_createWithX509ClientCert](#provisioning__sc__attestation__mechanism_8h_1a33e5f60fe5c7526a833696881248ee77)(const char * primary_cert,const char * secondary_cert)

#### attestationMechanism_createWithX509SigningCert 
[ATTESTATION_MECHANISM_HANDLE](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) [attestationMechanism_createWithX509SigningCert](#provisioning__sc__attestation__mechanism_8h_1ab26c8ccd3577148f3cf4d029f04eea9f)(const char * primary_cert,const char * secondary_cert)

#### attestationMechanism_createWithX509CAReference 
[ATTESTATION_MECHANISM_HANDLE](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) [attestationMechanism_createWithX509CAReference](#provisioning__sc__attestation__mechanism_8h_1ad42954f8303a9d848627fa37fa5a204c)(const char * primary_ref,const char * secondary_ref)

#### attestationMechanism_destroy 
void [attestationMechanism_destroy](#provisioning__sc__attestation__mechanism_8h_1ad66814a3291e09796ab0a68a46f6ecc4)([ATTESTATION_MECHANISM_HANDLE](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) att_mech)

#### attestationMechanism_isValidForIndividualEnrollment 
bool [attestationMechanism_isValidForIndividualEnrollment](#provisioning__sc__attestation__mechanism_8h_1a4a8ac61ae57957a38f7b1c4ea24565b9)([ATTESTATION_MECHANISM_HANDLE](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) att_mech)

#### attestationMechanism_isValidForEnrollmentGroup 
bool [attestationMechanism_isValidForEnrollmentGroup](#provisioning__sc__attestation__mechanism_8h_1afa1706c5c0bc2aea5e2a60e5e9dc13d5)([ATTESTATION_MECHANISM_HANDLE](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) att_mech)

#### attestationMechanism_getType 
[ATTESTATION_TYPE](#provisioning__sc__attestation__mechanism_8h_1a48a04269fd3dcfeeb6523c937b3b8760) [attestationMechanism_getType](#provisioning__sc__attestation__mechanism_8h_1a9a9608dce5e2cf814779112f4dd25d7e)([ATTESTATION_MECHANISM_HANDLE](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) att_mech)

#### attestationMechanism_getTpmAttestation 
[TPM_ATTESTATION_HANDLE](#provisioning__sc__tpm__attestation_8h_1a2160dafed7601d6f7f4ce726b8378a3c) [attestationMechanism_getTpmAttestation](#provisioning__sc__attestation__mechanism_8h_1a5e2e827890a378885d6e84f9198f7d92)([ATTESTATION_MECHANISM_HANDLE](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) att_mech)

#### attestationMechanism_getX509Attestation 
[X509_ATTESTATION_HANDLE](#provisioning__sc__x509__attestation_8h_1af73941413e975e31b577f9d6e420b156) [attestationMechanism_getX509Attestation](#provisioning__sc__attestation__mechanism_8h_1ac6983a874f053e32f537722839ef0a23)([ATTESTATION_MECHANISM_HANDLE](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) att_mech)

