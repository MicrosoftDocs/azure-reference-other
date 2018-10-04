# Header file provisioning_sc_enrollment.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/agenttime.h"  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include ["provisioning_sc_attestation_mechanism.h"](iot-c-ref-provisioning-sc-attestation-mechanism-h.md)  
\#include ["provisioning_sc_device_registration_state.h"](iot-c-ref-provisioning-sc-device-registration-state-h.md)  
\#include ["provisioning_sc_device_capabilities.h"](iot-c-ref-provisioning-sc-device-capabilities-h.md)  
\#include ["provisioning_sc_twin.h"](iot-c-ref-provisioning-sc-twin-h.md)  
\#include "parson.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[PROVISIONING_STATUSStrings](./iot-c-ref-provisioning-sc-enrollment-h/provisioning-statusstrings.md)            | 
[PROVISIONING_STATUS_FromString](./iot-c-ref-provisioning-sc-enrollment-h/provisioning-status-fromstring.md)            | 
[individualEnrollment_create](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-create.md)            | Creates an Individual Enrollment handle with a TPM Attestation for use in consequent APIs.
[individualEnrollment_destroy](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-destroy.md)            | Destroys an Individual Enrollment handle, freeing all associated memory. Please note that this also includes the attestation mechanism that was given in the constructor.
[enrollmentGroup_create](./iot-c-ref-provisioning-sc-enrollment-h/enrollmentgroup-create.md)            | Creates an Enrollment Group handle with an X509 Attestation for use in consequent APIs.
[enrollmentGroup_destroy](./iot-c-ref-provisioning-sc-enrollment-h/enrollmentgroup-destroy.md)            | Destorys an Enrollment Group handle, freeing all associated memory. Please note that this also includes the attestation mechanism that was given in the constructor.
[individualEnrollment_getAttestationMechanism](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-getattestationmechanism.md)            | 
[individualEnrollment_setAttestationMechanism](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-setattestationmechanism.md)            | 
[individualEnrollment_getInitialTwin](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-getinitialtwin.md)            | 
[individualEnrollment_setInitialTwin](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-setinitialtwin.md)            | 
[individualEnrollment_getDeviceCapabilities](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-getdevicecapabilities.md)            | 
[individualEnrollment_setDeviceCapabilities](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-setdevicecapabilities.md)            | 
[individualEnrollment_getDeviceRegistrationState](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-getdeviceregistrationstate.md)            | 
[individualEnrollment_getRegistrationId](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-getregistrationid.md)            | 
[individualEnrollment_getIotHubHostName](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-getiothubhostname.md)            | 
[individualEnrollment_getDeviceId](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-getdeviceid.md)            | 
[individualEnrollment_setDeviceId](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-setdeviceid.md)            | 
[individualEnrollment_getEtag](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-getetag.md)            | 
[individualEnrollment_setEtag](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-setetag.md)            | 
[individualEnrollment_getProvisioningStatus](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-getprovisioningstatus.md)            | 
[individualEnrollment_setProvisioningStatus](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-setprovisioningstatus.md)            | 
[individualEnrollment_getCreatedDateTime](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-getcreateddatetime.md)            | 
[individualEnrollment_getUpdatedDateTime](./iot-c-ref-provisioning-sc-enrollment-h/individualenrollment-getupdateddatetime.md)            | 
[enrollmentGroup_getAttestationMechanism](./iot-c-ref-provisioning-sc-enrollment-h/enrollmentgroup-getattestationmechanism.md)            | 
[enrollmentGroup_setAttestationMechanism](./iot-c-ref-provisioning-sc-enrollment-h/enrollmentgroup-setattestationmechanism.md)            | 
[enrollmentGroup_getInitialTwin](./iot-c-ref-provisioning-sc-enrollment-h/enrollmentgroup-getinitialtwin.md)            | 
[enrollmentGroup_setInitialTwin](./iot-c-ref-provisioning-sc-enrollment-h/enrollmentgroup-setinitialtwin.md)            | 
[enrollmentGroup_getGroupId](./iot-c-ref-provisioning-sc-enrollment-h/enrollmentgroup-getgroupid.md)            | 
[enrollmentGroup_getIotHubHostName](./iot-c-ref-provisioning-sc-enrollment-h/enrollmentgroup-getiothubhostname.md)            | 
[enrollmentGroup_getEtag](./iot-c-ref-provisioning-sc-enrollment-h/enrollmentgroup-getetag.md)            | 
[enrollmentGroup_setEtag](./iot-c-ref-provisioning-sc-enrollment-h/enrollmentgroup-setetag.md)            | 
[enrollmentGroup_getProvisioningStatus](./iot-c-ref-provisioning-sc-enrollment-h/enrollmentgroup-getprovisioningstatus.md)            | 
[enrollmentGroup_setProvisioningStatus](./iot-c-ref-provisioning-sc-enrollment-h/enrollmentgroup-setprovisioningstatus.md)            | 
[enrollmentGroup_getCreatedDateTime](./iot-c-ref-provisioning-sc-enrollment-h/enrollmentgroup-getcreateddatetime.md)            | 
[enrollmentGroup_getUpdatedDateTime](./iot-c-ref-provisioning-sc-enrollment-h/enrollmentgroup-getupdateddatetime.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
PROVISIONING_STATUS_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
INDIVIDUAL_ENROLLMENT_HANDLE            | Handles to hide structs and use them in consequent APIs.
ENROLLMENT_GROUP_HANDLE            | 

