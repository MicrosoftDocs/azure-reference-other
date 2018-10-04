# Header file provisioning_sc_x509_attestation.h 

Stub comment for brief. Please update this comment.

## Includes

\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include "parson.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[X509_CERTIFICATE_TYPEStrings](./iot-c-ref-provisioning-sc-x509-attestation-h/x509-certificate-typestrings.md)            | 
[X509_CERTIFICATE_TYPE_FromString](./iot-c-ref-provisioning-sc-x509-attestation-h/x509-certificate-type-fromstring.md)            | 
[x509Attestation_getCertificateType](./iot-c-ref-provisioning-sc-x509-attestation-h/x509attestation-getcertificatetype.md)            | 
[x509Attestation_getPrimaryCertificate](./iot-c-ref-provisioning-sc-x509-attestation-h/x509attestation-getprimarycertificate.md)            | 
[x509Attestation_getSecondaryCertificate](./iot-c-ref-provisioning-sc-x509-attestation-h/x509attestation-getsecondarycertificate.md)            | 
[x509Certificate_getSubjectName](./iot-c-ref-provisioning-sc-x509-attestation-h/x509certificate-getsubjectname.md)            | 
[x509Certificate_getSha1Thumbprint](./iot-c-ref-provisioning-sc-x509-attestation-h/x509certificate-getsha1thumbprint.md)            | 
[x509Certificate_getSha256Thumbprint](./iot-c-ref-provisioning-sc-x509-attestation-h/x509certificate-getsha256thumbprint.md)            | 
[x509Certificate_getIssuerName](./iot-c-ref-provisioning-sc-x509-attestation-h/x509certificate-getissuername.md)            | 
[x509Certificate_getNotBeforeUtc](./iot-c-ref-provisioning-sc-x509-attestation-h/x509certificate-getnotbeforeutc.md)            | 
[x509Certificate_getNotAfterUtc](./iot-c-ref-provisioning-sc-x509-attestation-h/x509certificate-getnotafterutc.md)            | 
[x509Certificate_getSerialNumber](./iot-c-ref-provisioning-sc-x509-attestation-h/x509certificate-getserialnumber.md)            | 
[x509Certificate_getVersion](./iot-c-ref-provisioning-sc-x509-attestation-h/x509certificate-getversion.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
X509_CERTIFICATE_TYPE_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
X509_ATTESTATION_HANDLE            | 
X509_CERTIFICATE_HANDLE            | 

## Function documentation

#### X509_CERTIFICATE_TYPEStrings 
const char * [X509_CERTIFICATE_TYPEStrings](#provisioning__sc__x509__attestation_8h_1a4009cc46ef67a990dd12ecf39906eee7)([X509_CERTIFICATE_TYPE](#provisioning__sc__x509__attestation_8h_1a352fbebcee50679dd88a6745b1ce70cc) value)

#### X509_CERTIFICATE_TYPE_FromString 
int [X509_CERTIFICATE_TYPE_FromString](#provisioning__sc__x509__attestation_8h_1a1176a1bdf2d4cfb398d4e7109a9b7002)(const char * enumAsString,[X509_CERTIFICATE_TYPE](#provisioning__sc__x509__attestation_8h_1a352fbebcee50679dd88a6745b1ce70cc) * destination)

#### x509Attestation_getCertificateType 
[X509_CERTIFICATE_TYPE](#provisioning__sc__x509__attestation_8h_1a352fbebcee50679dd88a6745b1ce70cc) [x509Attestation_getCertificateType](#provisioning__sc__x509__attestation_8h_1a886cb14d8940122f578e0e15fdfdd66e)([X509_ATTESTATION_HANDLE](#provisioning__sc__x509__attestation_8h_1af73941413e975e31b577f9d6e420b156) x509_att)

#### x509Attestation_getPrimaryCertificate 
[X509_CERTIFICATE_HANDLE](#provisioning__sc__x509__attestation_8h_1a2e8d12cba13a8890ab37197c1e6e0303) [x509Attestation_getPrimaryCertificate](#provisioning__sc__x509__attestation_8h_1a078ccad91448722c029981d23b9cbc51)([X509_ATTESTATION_HANDLE](#provisioning__sc__x509__attestation_8h_1af73941413e975e31b577f9d6e420b156) x509_att)

#### x509Attestation_getSecondaryCertificate 
[X509_CERTIFICATE_HANDLE](#provisioning__sc__x509__attestation_8h_1a2e8d12cba13a8890ab37197c1e6e0303) [x509Attestation_getSecondaryCertificate](#provisioning__sc__x509__attestation_8h_1a33cac69c8fc633ae74a79801f9f90aab)([X509_ATTESTATION_HANDLE](#provisioning__sc__x509__attestation_8h_1af73941413e975e31b577f9d6e420b156) x509_att)

#### x509Certificate_getSubjectName 
const char * [x509Certificate_getSubjectName](#provisioning__sc__x509__attestation_8h_1a37c7a4b7201ebc92e5eb1e04db4aaf9f)([X509_CERTIFICATE_HANDLE](#provisioning__sc__x509__attestation_8h_1a2e8d12cba13a8890ab37197c1e6e0303) x509_cert)

#### x509Certificate_getSha1Thumbprint 
const char * [x509Certificate_getSha1Thumbprint](#provisioning__sc__x509__attestation_8h_1a9689f0941427dad7686fe9522974026a)([X509_CERTIFICATE_HANDLE](#provisioning__sc__x509__attestation_8h_1a2e8d12cba13a8890ab37197c1e6e0303) x509_cert)

#### x509Certificate_getSha256Thumbprint 
const char * [x509Certificate_getSha256Thumbprint](#provisioning__sc__x509__attestation_8h_1ac70a8bec6768128edd56ff585a2c8ba2)([X509_CERTIFICATE_HANDLE](#provisioning__sc__x509__attestation_8h_1a2e8d12cba13a8890ab37197c1e6e0303) x509_cert)

#### x509Certificate_getIssuerName 
const char * [x509Certificate_getIssuerName](#provisioning__sc__x509__attestation_8h_1adffe62e9462aa7623aeff6d2e86d9eec)([X509_CERTIFICATE_HANDLE](#provisioning__sc__x509__attestation_8h_1a2e8d12cba13a8890ab37197c1e6e0303) x509_cert)

#### x509Certificate_getNotBeforeUtc 
const char * [x509Certificate_getNotBeforeUtc](#provisioning__sc__x509__attestation_8h_1ae99fb8afd47be7c7a6b3cabb6044c08c)([X509_CERTIFICATE_HANDLE](#provisioning__sc__x509__attestation_8h_1a2e8d12cba13a8890ab37197c1e6e0303) x509_cert)

#### x509Certificate_getNotAfterUtc 
const char * [x509Certificate_getNotAfterUtc](#provisioning__sc__x509__attestation_8h_1a16f24cf625f2577204feeb4bb95758bf)([X509_CERTIFICATE_HANDLE](#provisioning__sc__x509__attestation_8h_1a2e8d12cba13a8890ab37197c1e6e0303) x509_cert)

#### x509Certificate_getSerialNumber 
const char * [x509Certificate_getSerialNumber](#provisioning__sc__x509__attestation_8h_1a1ea076de1e589dd7e5b99f2644146332)([X509_CERTIFICATE_HANDLE](#provisioning__sc__x509__attestation_8h_1a2e8d12cba13a8890ab37197c1e6e0303) x509_cert)

#### x509Certificate_getVersion 
int [x509Certificate_getVersion](#provisioning__sc__x509__attestation_8h_1a2a5e864859ee9763611d22dd7b5dd887)([X509_CERTIFICATE_HANDLE](#provisioning__sc__x509__attestation_8h_1a2e8d12cba13a8890ab37197c1e6e0303) x509_cert)

