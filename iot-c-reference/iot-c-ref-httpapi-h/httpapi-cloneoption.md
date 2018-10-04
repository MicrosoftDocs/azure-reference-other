# HTTPAPI_CloneOption()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/httpapi.h"](../iot-c-ref-httpapi-h.md)  

[`HTTPAPI_RESULT`](#httpapi_8h_1ae6d85e45d7bb89c3692f17750762557e) `[`HTTPAPI_CloneOption`](#httpapi_8h_1ad4a4aab991408a4dbf0c018eae727985)(const char * optionName,const void * value,const void ** savedValue)`

Clones the option named `optionName` bearing the value `value` into the pointer `savedValue`.

#### Parameters
* `optionName` A `NULL` terminated string representing the name of the option 

* `value` A pointer to the value of the option. 

* `savedValue` This pointer receives the copy of the value of the option. The copy needs to be free-able.

#### Returns
`HTTPAPI_OK` if initialization is successful or an error code in case it fails.

