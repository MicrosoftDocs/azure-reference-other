# httpapi.h 

This module implements the standard HTTP API used by the C IoT client library.

## Includes

\#include "azure_c_shared_utility/httpheaders.h"  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include "azure_c_shared_utility/buffer_.h"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include <stddef.h>  

## Detailed Description

For example, on the Windows platform the HTTP API code uses WinHTTP and for Linux it uses curl and so forth. HTTPAPI must support HTTPs (HTTP+SSL).

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[HTTPAPI_RESULTStrings](./iot-c-ref-httpapi-h/httpapi-resultstrings.md)            | 
[HTTPAPI_RESULT_FromString](./iot-c-ref-httpapi-h/httpapi-result-fromstring.md)            | 
[HTTPAPI_REQUEST_TYPEStrings](./iot-c-ref-httpapi-h/httpapi-request-typestrings.md)            | 
[HTTPAPI_REQUEST_TYPE_FromString](./iot-c-ref-httpapi-h/httpapi-request-type-fromstring.md)            | 
[HTTPAPI_Init](./iot-c-ref-httpapi-h/httpapi-init.md)            | Global initialization for the HTTP API component.
[HTTPAPI_Deinit](./iot-c-ref-httpapi-h/httpapi-deinit.md)            | Free resources allocated in [HTTPAPI_Init](#httpapi_8h_1a0a73dc1b76c522a36b0f201d1a80c3d4).
[HTTPAPI_CreateConnection](./iot-c-ref-httpapi-h/httpapi-createconnection.md)            | Creates an HTTPS connection to the host specified by the `hostName` parameter.
[HTTPAPI_CloseConnection](./iot-c-ref-httpapi-h/httpapi-closeconnection.md)            | Closes a connection created with [HTTPAPI_CreateConnection](#httpapi_8h_1a96629fdbe1b52a5357da60bb1248b174).
[HTTPAPI_ExecuteRequest](./iot-c-ref-httpapi-h/httpapi-executerequest.md)            | Sends the HTTP request to the host and handles the response for the HTTP call.
[HTTPAPI_SetOption](./iot-c-ref-httpapi-h/httpapi-setoption.md)            | Sets the option named `optionName` bearing the value `value` for the HTTP_HANDLE `handle`.
[HTTPAPI_CloneOption](./iot-c-ref-httpapi-h/httpapi-cloneoption.md)            | Clones the option named `optionName` bearing the value `value` into the pointer `savedValue`.

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
AMBIGUOUS_STATUS_CODE            | 
HTTPAPI_RESULT_VALUES            | 
HTTPAPI_REQUEST_TYPE_VALUES            | 
MAX_HOSTNAME_LEN            | 
MAX_USERNAME_LEN            | 
MAX_PASSWORD_LEN            | 

## Typedefs

####HTTP_HANDLE
typedef struct HTTP_HANDLE_DATA_TAG * HTTP_HANDLE()

