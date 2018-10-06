# provisioning_sc_x509_attestation.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
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

## Macro definitions

#### X509_CERTIFICATE_TYPE_VALUES

```C
#define X509_CERTIFICATE_TYPE_VALUES \
        X509_CERTIFICATE_TYPE_NONE, \
        X509_CERTIFICATE_TYPE_CLIENT, \
        X509_CERTIFICATE_TYPE_SIGNING, \
        X509_CERTIFICATE_TYPE_CA_REFERENCES 
```

## Enumeration types

#### X509_CERTIFICATE_TYPE

```C
enum X509_CERTIFICATE_TYPE {
  X509_CERTIFICATE_TYPE_NONE,
  X509_CERTIFICATE_TYPE_CLIENT,
  X509_CERTIFICATE_TYPE_SIGNING,
  X509_CERTIFICATE_TYPE_CA_REFERENCES
}
```
Constant                    | Description                                
----------------------------|----------------
 X509_CERTIFICATE_TYPE_NONE            | 
 X509_CERTIFICATE_TYPE_CLIENT            | 
 X509_CERTIFICATE_TYPE_SIGNING            | 
 X509_CERTIFICATE_TYPE_CA_REFERENCES            | 

## Type definitions

#### X509_ATTESTATION_HANDLE

```C
typedef struct X509_ATTESTATION_TAG* X509_ATTESTATION_HANDLE;
```

#### X509_CERTIFICATE_HANDLE

```C
typedef struct X509_CERTIFICATE_WITH_INFO_TAG* X509_CERTIFICATE_HANDLE;
```

