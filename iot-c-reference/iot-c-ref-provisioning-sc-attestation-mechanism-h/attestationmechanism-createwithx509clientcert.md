# attestationMechanism_createWithX509ClientCert()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_attestation_mechanism.h"](../iot-c-ref-provisioning-sc-attestation-mechanism-h.md)  

[`ATTESTATION_MECHANISM_HANDLE`](#provisioning__sc__attestation__mechanism_8h_1adba99be7269bb68c4f8d2687bd4992b8) `[`attestationMechanism_createWithX509ClientCert`](#provisioning__sc__attestation__mechanism_8h_1a33e5f60fe5c7526a833696881248ee77)(const char * primary_cert,const char * secondary_cert)`

Creates an Attestation Mechanism handle that uses an x509 Attestation with client certificate(s) for use in consequent APIs. Please note that an x509 Attestation with a client certificate is NOT VALID when attached to an enrollment group.

#### Parameters
* `primary_cert` A primary certificate for use with the x509. 

* `secondary_cert` A secondary certificate for use with the x509 (optional - if not using two certs, pass NULL).

#### Returns
A non NULL handle representing an Attestation Mechanism using an X509 Attestation with a client certificate, and NULL on failure.

