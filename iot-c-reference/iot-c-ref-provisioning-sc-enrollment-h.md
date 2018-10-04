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

## Function documentation

#### PROVISIONING_STATUSStrings 
const char * [PROVISIONING_STATUSStrings](#provisioning__sc__enrollment_8h_1aa8e54de39da7c13ca0b65052f7658d19)([PROVISIONING_STATUS](#provisioning__sc__enrollment_8h_1a48d94db5bbc47b58882c5c23b95e87d7) value)

#### PROVISIONING_STATUS_FromString 
int [PROVISIONING_STATUS_FromString](#provisioning__sc__enrollment_8h_1a7fc927d6b41c9e73cbbab2d2520fb52c)(const char * enumAsString,[PROVISIONING_STATUS](#provisioning__sc__enrollment_8h_1a48d94db5bbc47b58882c5c23b95e87d7) * destination)

#### individualEnrollment_create 
[INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) [individualEnrollment_create](#provisioning__sc__enrollment_8h_1a070ace8d9abad98df60f17410bc4a945)(const char * reg_id,[ATTESTATION_MECHANISM_HANDLE](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) att_mech)

#### individualEnrollment_destroy 
void [individualEnrollment_destroy](#provisioning__sc__enrollment_8h_1a8c043d2c029a3bb1ed500dcdb6303c1f)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)

#### enrollmentGroup_create 
[ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) [enrollmentGroup_create](#provisioning__sc__enrollment_8h_1a67af9532e246f745aa12f07093f99c31)(const char * group_id,[ATTESTATION_MECHANISM_HANDLE](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) att_mech)

#### enrollmentGroup_destroy 
void [enrollmentGroup_destroy](#provisioning__sc__enrollment_8h_1a6531ce2323081afbcfceaa1d1c0db74c)([ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment)

#### individualEnrollment_getAttestationMechanism 
[ATTESTATION_MECHANISM_HANDLE](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) [individualEnrollment_getAttestationMechanism](#provisioning__sc__enrollment_8h_1aa307027c5b08fee2787a99c49989c952)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)

#### individualEnrollment_setAttestationMechanism 
int [individualEnrollment_setAttestationMechanism](#provisioning__sc__enrollment_8h_1a269d0d5eefc6a1b27202862d2a6a42f4)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment,[ATTESTATION_MECHANISM_HANDLE](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) att_mech)

#### individualEnrollment_getInitialTwin 
[INITIAL_TWIN_HANDLE](#provisioning__sc__twin_8h_1a8230047b4f4613e6691e5a741e65797f) [individualEnrollment_getInitialTwin](#provisioning__sc__enrollment_8h_1a28bc12f381703cc98b26e82a9a43e7c4)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)

#### individualEnrollment_setInitialTwin 
int [individualEnrollment_setInitialTwin](#provisioning__sc__enrollment_8h_1a88b21855ce1107ee471749bd218556cb)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment,[INITIAL_TWIN_HANDLE](#provisioning__sc__twin_8h_1a8230047b4f4613e6691e5a741e65797f) twin)

#### individualEnrollment_getDeviceCapabilities 
[DEVICE_CAPABILITIES_HANDLE](#provisioning__sc__device__capabilities_8h_1af33545b05ae4501337bcfeaecce34ae4) [individualEnrollment_getDeviceCapabilities](#provisioning__sc__enrollment_8h_1a1ae2b5cb5a92e105d301f6e9e1d8157c)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)

#### individualEnrollment_setDeviceCapabilities 
int [individualEnrollment_setDeviceCapabilities](#provisioning__sc__enrollment_8h_1a26a2586ac6c42f1ae69c3301f9063757)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment,[DEVICE_CAPABILITIES_HANDLE](#provisioning__sc__device__capabilities_8h_1af33545b05ae4501337bcfeaecce34ae4) capabilities)

#### individualEnrollment_getDeviceRegistrationState 
[DEVICE_REGISTRATION_STATE_HANDLE](#provisioning__sc__device__registration__state_8h_1a52841b38d699231f85846525109d2804) [individualEnrollment_getDeviceRegistrationState](#provisioning__sc__enrollment_8h_1ab1bde1ad4145cb479227472a6ba0e1e4)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)

#### individualEnrollment_getRegistrationId 
const char * [individualEnrollment_getRegistrationId](#provisioning__sc__enrollment_8h_1acecaa4c024eb4e2ef9c3b8186776d7e6)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)

#### individualEnrollment_getIotHubHostName 
const char * [individualEnrollment_getIotHubHostName](#provisioning__sc__enrollment_8h_1a14189af08889d3e53d041afaa160d465)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)

#### individualEnrollment_getDeviceId 
const char * [individualEnrollment_getDeviceId](#provisioning__sc__enrollment_8h_1a7c2079f5c2f3becd7fd7c36ad6068791)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)

#### individualEnrollment_setDeviceId 
int [individualEnrollment_setDeviceId](#provisioning__sc__enrollment_8h_1a3e44539e6e11f6b8b55b69ab20a22704)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment,const char * device_id)

#### individualEnrollment_getEtag 
const char * [individualEnrollment_getEtag](#provisioning__sc__enrollment_8h_1aa30b57455294d6a60dc34e25e7e10f54)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)

#### individualEnrollment_setEtag 
int [individualEnrollment_setEtag](#provisioning__sc__enrollment_8h_1a7e7f9a28a0c672ac03dd48ccd5b7015a)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment,const char * etag)

#### individualEnrollment_getProvisioningStatus 
[PROVISIONING_STATUS](#provisioning__sc__enrollment_8h_1a48d94db5bbc47b58882c5c23b95e87d7) [individualEnrollment_getProvisioningStatus](#provisioning__sc__enrollment_8h_1a9018e4400ce67a55b0bf37119417c5ce)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)

#### individualEnrollment_setProvisioningStatus 
int [individualEnrollment_setProvisioningStatus](#provisioning__sc__enrollment_8h_1a430172e21c254fda4aeb146a4e5d6a7c)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment,[PROVISIONING_STATUS](#provisioning__sc__enrollment_8h_1a48d94db5bbc47b58882c5c23b95e87d7) prov_status)

#### individualEnrollment_getCreatedDateTime 
const char * [individualEnrollment_getCreatedDateTime](#provisioning__sc__enrollment_8h_1a43ff141e9a203dbd4ecda8d55019c202)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)

#### individualEnrollment_getUpdatedDateTime 
const char * [individualEnrollment_getUpdatedDateTime](#provisioning__sc__enrollment_8h_1a9b20fa704961d332a5d750d92e683d2d)([INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)

#### enrollmentGroup_getAttestationMechanism 
[ATTESTATION_MECHANISM_HANDLE](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) [enrollmentGroup_getAttestationMechanism](#provisioning__sc__enrollment_8h_1a7d1974891c4403b6f6d054edd8856267)([ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment)

#### enrollmentGroup_setAttestationMechanism 
int [enrollmentGroup_setAttestationMechanism](#provisioning__sc__enrollment_8h_1a322d198b9b9c38c2361401a15f1b0522)([ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment,[ATTESTATION_MECHANISM_HANDLE](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) att_mech)

#### enrollmentGroup_getInitialTwin 
[INITIAL_TWIN_HANDLE](#provisioning__sc__twin_8h_1a8230047b4f4613e6691e5a741e65797f) [enrollmentGroup_getInitialTwin](#provisioning__sc__enrollment_8h_1a055035a6c7847cca34256a85ec6dfaef)([ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment)

#### enrollmentGroup_setInitialTwin 
int [enrollmentGroup_setInitialTwin](#provisioning__sc__enrollment_8h_1a89e4bbc8ab7143e6090c2f63b40988e4)([ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment,[INITIAL_TWIN_HANDLE](#provisioning__sc__twin_8h_1a8230047b4f4613e6691e5a741e65797f) twin)

#### enrollmentGroup_getGroupId 
const char * [enrollmentGroup_getGroupId](#provisioning__sc__enrollment_8h_1a6e3d84ed369f48f1ec26b41baa3d002e)([ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment)

#### enrollmentGroup_getIotHubHostName 
const char * [enrollmentGroup_getIotHubHostName](#provisioning__sc__enrollment_8h_1a3c87f873b934e7730b513899190594e9)([ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment)

#### enrollmentGroup_getEtag 
const char * [enrollmentGroup_getEtag](#provisioning__sc__enrollment_8h_1a0fe839d1e4bf61542ee22e3b02a52024)([ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment)

#### enrollmentGroup_setEtag 
int [enrollmentGroup_setEtag](#provisioning__sc__enrollment_8h_1a9c482a8ed7d30f9389c7c5d329160b7c)([ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment,const char * etag)

#### enrollmentGroup_getProvisioningStatus 
[PROVISIONING_STATUS](#provisioning__sc__enrollment_8h_1a48d94db5bbc47b58882c5c23b95e87d7) [enrollmentGroup_getProvisioningStatus](#provisioning__sc__enrollment_8h_1ad6b1beed2f0689982fc48912f81ef7f2)([ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment)

#### enrollmentGroup_setProvisioningStatus 
int [enrollmentGroup_setProvisioningStatus](#provisioning__sc__enrollment_8h_1aef9b0a4ad971f70a25677222ee4f28e7)([ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment,[PROVISIONING_STATUS](#provisioning__sc__enrollment_8h_1a48d94db5bbc47b58882c5c23b95e87d7) prov_status)

#### enrollmentGroup_getCreatedDateTime 
const char * [enrollmentGroup_getCreatedDateTime](#provisioning__sc__enrollment_8h_1aa6965924d17ff5f32bf7de410de9e236)([ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment)

#### enrollmentGroup_getUpdatedDateTime 
const char * [enrollmentGroup_getUpdatedDateTime](#provisioning__sc__enrollment_8h_1ae7cb463d4654932d351a16c4e4014f2c)([ENROLLMENT_GROUP_HANDLE](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment)

