# HTTPAPI_SetOption()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/httpapi.h"](../iot-c-ref-httpapi-h.md)  

**[HTTPAPI_RESULT](#httpapi_8h_1ae6d85e45d7bb89c3692f17750762557e) [HTTPAPI_SetOption](#httpapi_8h_1a126e89db045f53ecc3438eecea2efc84)([HTTP_HANDLE](#httpapi_8h_1a3b2d2d7095a41a942705e437133d35dc) handle,const char * optionName,const void * value)**

Sets the option named `optionName` bearing the value `value` for the HTTP_HANDLE `handle`.

#### Parameters
* `handle` The handle to the HTTP connection created via [HTTPAPI_CreateConnection](#httpapi_8h_1a96629fdbe1b52a5357da60bb1248b174). 

* `optionName` A `NULL` terminated string representing the name of the option. 

* `value` A pointer to the value for the option.

#### Returns
`HTTPAPI_OK` if initialization is successful or an error code in case it fails.

