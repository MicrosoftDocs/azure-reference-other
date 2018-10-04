# Header file httpapi.h 

This module implements the standard HTTP API used by the C IoT client library.

## Includes

\#include "azure_c_shared_utility/httpheaders.h"  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include "azure_c_shared_utility/buffer_.h"  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
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

Typedef                        | Value                                
--------------------------------|---------------------------------------------
HTTP_HANDLE            | 

## Function documentation

#### HTTPAPI_RESULTStrings 
const char * [HTTPAPI_RESULTStrings](#httpapi_8h_1a1e287bdc44b466d745bdabe6d8d19c7a)([HTTPAPI_RESULT](#httpapi_8h_1ae6d85e45d7bb89c3692f17750762557e) value)

#### HTTPAPI_RESULT_FromString 
int [HTTPAPI_RESULT_FromString](#httpapi_8h_1a08dc400f4b9d0d8123092232630aa5e3)(const char * enumAsString,[HTTPAPI_RESULT](#httpapi_8h_1ae6d85e45d7bb89c3692f17750762557e) * destination)

#### HTTPAPI_REQUEST_TYPEStrings 
const char * [HTTPAPI_REQUEST_TYPEStrings](#httpapi_8h_1ae5273964cc4096a21694c792013131d3)([HTTPAPI_REQUEST_TYPE](#httpapi_8h_1a7d55a20aafcc43be8d9a737dcbefd5ad) value)

#### HTTPAPI_REQUEST_TYPE_FromString 
int [HTTPAPI_REQUEST_TYPE_FromString](#httpapi_8h_1ad68638ee1e4bad65743aa0cde8dec331)(const char * enumAsString,[HTTPAPI_REQUEST_TYPE](#httpapi_8h_1a7d55a20aafcc43be8d9a737dcbefd5ad) * destination)

#### HTTPAPI_Init 
[HTTPAPI_RESULT](#httpapi_8h_1ae6d85e45d7bb89c3692f17750762557e) [HTTPAPI_Init](#httpapi_8h_1a0a73dc1b76c522a36b0f201d1a80c3d4)(void)

#### HTTPAPI_Deinit 
void [HTTPAPI_Deinit](#httpapi_8h_1a0746eed2ddbd3cf46ec5f015ceb32305)(void)

#### HTTPAPI_CreateConnection 
[HTTP_HANDLE](#httpapi_8h_1a3b2d2d7095a41a942705e437133d35dc) [HTTPAPI_CreateConnection](#httpapi_8h_1a96629fdbe1b52a5357da60bb1248b174)(const char * hostName)

#### HTTPAPI_CloseConnection 
void [HTTPAPI_CloseConnection](#httpapi_8h_1aed5a7f4253357457399d03dad763d904)([HTTP_HANDLE](#httpapi_8h_1a3b2d2d7095a41a942705e437133d35dc) handle)

#### HTTPAPI_ExecuteRequest 
[HTTPAPI_RESULT](#httpapi_8h_1ae6d85e45d7bb89c3692f17750762557e) [HTTPAPI_ExecuteRequest](#httpapi_8h_1afa60b8d96e73b2fe592b591208ef66b1)([HTTP_HANDLE](#httpapi_8h_1a3b2d2d7095a41a942705e437133d35dc) handle,[HTTPAPI_REQUEST_TYPE](#httpapi_8h_1a7d55a20aafcc43be8d9a737dcbefd5ad) requestType,const char * relativePath,HTTP_HEADERS_HANDLE httpHeadersHandle,const unsigned char * content,size_t contentLength,unsigned int * statusCode,HTTP_HEADERS_HANDLE responseHeadersHandle,BUFFER_HANDLE responseContent)

#### HTTPAPI_SetOption 
[HTTPAPI_RESULT](#httpapi_8h_1ae6d85e45d7bb89c3692f17750762557e) [HTTPAPI_SetOption](#httpapi_8h_1a126e89db045f53ecc3438eecea2efc84)([HTTP_HANDLE](#httpapi_8h_1a3b2d2d7095a41a942705e437133d35dc) handle,const char * optionName,const void * value)

#### HTTPAPI_CloneOption 
[HTTPAPI_RESULT](#httpapi_8h_1ae6d85e45d7bb89c3692f17750762557e) [HTTPAPI_CloneOption](#httpapi_8h_1ad4a4aab991408a4dbf0c018eae727985)(const char * optionName,const void * value,const void ** savedValue)

