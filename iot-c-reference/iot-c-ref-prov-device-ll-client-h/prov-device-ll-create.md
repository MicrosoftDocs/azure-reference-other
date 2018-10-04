# Prov_Device_LL_Create()

\#include ["azure-iot-sdk-c/provisioning_client/inc/azure_prov_client/prov_device_ll_client.h"](../iot-c-ref-prov-device-ll-client-h.md)  

**[PROV_DEVICE_LL_HANDLE](#prov__device__ll__client_8h_1aa6ce77119fc5a0c50d57a97a990cb54f) [Prov_Device_LL_Create](#prov__device__ll__client_8h_1a9f209da792720540561a27a5f82d62b2)(const char * uri,const char * scope_id,[PROV_DEVICE_TRANSPORT_PROVIDER_FUNCTION](#prov__device__ll__client_8h_1a6464d6b187cc71ac6e81938338d31d48) protocol)**

Creates a Provisioning Client for communications with the Device Provisioning Client Service.

#### Parameters
* `uri` The URI of the Device Provisioning Service 

* `scope_id` The customer specific Id Scope 

* `protocol` Function pointer for protocol implementation

#### Returns
A non-NULL PROV_DEVICE_LL_HANDLE value that is used when invoking other functions and NULL on Failure

