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
[HTTPAPI_Deinit](./iot-c-ref-httpapi-h/httpapi-deinit.md)            | Free resources allocated in [HTTPAPI_Init](function (refid) {<br/>      if ((options.groups \|\| options.classes) && compound.refid !== refid && references[refid]) {<br/>        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;<br/>      } else {<br/>        return '#' + refid;<br/>      }<br/>    }).
[HTTPAPI_CreateConnection](./iot-c-ref-httpapi-h/httpapi-createconnection.md)            | Creates an HTTPS connection to the host specified by the `hostName` parameter.
[HTTPAPI_CloseConnection](./iot-c-ref-httpapi-h/httpapi-closeconnection.md)            | Closes a connection created with [HTTPAPI_CreateConnection](function (refid) {<br/>      if ((options.groups \|\| options.classes) && compound.refid !== refid && references[refid]) {<br/>        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;<br/>      } else {<br/>        return '#' + refid;<br/>      }<br/>    }).
[HTTPAPI_ExecuteRequest](./iot-c-ref-httpapi-h/httpapi-executerequest.md)            | Sends the HTTP request to the host and handles the response for the HTTP call.
[HTTPAPI_SetOption](./iot-c-ref-httpapi-h/httpapi-setoption.md)            | Sets the option named `optionName` bearing the value `value` for the HTTP_HANDLE `handle`.
[HTTPAPI_CloneOption](./iot-c-ref-httpapi-h/httpapi-cloneoption.md)            | Clones the option named `optionName` bearing the value `value` into the pointer `savedValue`.

## Macro definitions

#### AMBIGUOUS_STATUS_CODE

```C
#define AMBIGUOUS_STATUS_CODE (300) 

```

#### HTTPAPI_RESULT_VALUES

```C
#define HTTPAPI_RESULT_VALUES \
 HTTPAPI_OK, \
 HTTPAPI_INVALID_ARG, \
 HTTPAPI_ERROR, \
 HTTPAPI_OPEN_REQUEST_FAILED, \
 HTTPAPI_SET_OPTION_FAILED, \
 HTTPAPI_SEND_REQUEST_FAILED, \
 HTTPAPI_RECEIVE_RESPONSE_FAILED, \
 HTTPAPI_QUERY_HEADERS_FAILED, \
 HTTPAPI_QUERY_DATA_AVAILABLE_FAILED, \
 HTTPAPI_READ_DATA_FAILED, \
 HTTPAPI_ALREADY_INIT, \
 HTTPAPI_NOT_INIT, \
 HTTPAPI_HTTP_HEADERS_FAILED, \
 HTTPAPI_STRING_PROCESSING_ERROR, \
 HTTPAPI_ALLOC_FAILED, \
 HTTPAPI_INIT_FAILED, \
 HTTPAPI_INSUFFICIENT_RESPONSE_BUFFER, \
 HTTPAPI_SET_X509_FAILURE, \
 HTTPAPI_SET_TIMEOUTS_FAILED 

```

#### HTTPAPI_REQUEST_TYPE_VALUES

```C
#define HTTPAPI_REQUEST_TYPE_VALUES \
 HTTPAPI_REQUEST_GET, \
 HTTPAPI_REQUEST_POST, \
 HTTPAPI_REQUEST_PUT, \
 HTTPAPI_REQUEST_DELETE, \
 HTTPAPI_REQUEST_PATCH, \
 HTTPAPI_REQUEST_HEAD 

```

#### MAX_HOSTNAME_LEN

```C
#define MAX_HOSTNAME_LEN 65 

```

#### MAX_USERNAME_LEN

```C
#define MAX_USERNAME_LEN 65 

```

#### MAX_PASSWORD_LEN

```C
#define MAX_PASSWORD_LEN 65 

```

## Enumeration types

#### HTTPAPI_RESULT

Enumeration specifying the possible return values for the APIs in this module. 

```C
enum HTTPAPI_RESULT {
  HTTPAPI_OK,
  HTTPAPI_INVALID_ARG,
  HTTPAPI_ERROR,
  HTTPAPI_OPEN_REQUEST_FAILED,
  HTTPAPI_SET_OPTION_FAILED,
  HTTPAPI_SEND_REQUEST_FAILED,
  HTTPAPI_RECEIVE_RESPONSE_FAILED,
  HTTPAPI_QUERY_HEADERS_FAILED,
  HTTPAPI_QUERY_DATA_AVAILABLE_FAILED,
  HTTPAPI_READ_DATA_FAILED,
  HTTPAPI_ALREADY_INIT,
  HTTPAPI_NOT_INIT,
  HTTPAPI_HTTP_HEADERS_FAILED,
  HTTPAPI_STRING_PROCESSING_ERROR,
  HTTPAPI_ALLOC_FAILED,
  HTTPAPI_INIT_FAILED,
  HTTPAPI_INSUFFICIENT_RESPONSE_BUFFER,
  HTTPAPI_SET_X509_FAILURE,
  HTTPAPI_SET_TIMEOUTS_FAILED
}

```
Constant                    | Description                                
----------------------------|----------------
 HTTPAPI_OK            | 
 HTTPAPI_INVALID_ARG            | 
 HTTPAPI_ERROR            | 
 HTTPAPI_OPEN_REQUEST_FAILED            | 
 HTTPAPI_SET_OPTION_FAILED            | 
 HTTPAPI_SEND_REQUEST_FAILED            | 
 HTTPAPI_RECEIVE_RESPONSE_FAILED            | 
 HTTPAPI_QUERY_HEADERS_FAILED            | 
 HTTPAPI_QUERY_DATA_AVAILABLE_FAILED            | 
 HTTPAPI_READ_DATA_FAILED            | 
 HTTPAPI_ALREADY_INIT            | 
 HTTPAPI_NOT_INIT            | 
 HTTPAPI_HTTP_HEADERS_FAILED            | 
 HTTPAPI_STRING_PROCESSING_ERROR            | 
 HTTPAPI_ALLOC_FAILED            | 
 HTTPAPI_INIT_FAILED            | 
 HTTPAPI_INSUFFICIENT_RESPONSE_BUFFER            | 
 HTTPAPI_SET_X509_FAILURE            | 
 HTTPAPI_SET_TIMEOUTS_FAILED            | 

#### HTTPAPI_REQUEST_TYPE

Enumeration specifying the HTTP request verbs accepted by the HTTPAPI module. 

```C
enum HTTPAPI_REQUEST_TYPE {
  HTTPAPI_REQUEST_GET,
  HTTPAPI_REQUEST_POST,
  HTTPAPI_REQUEST_PUT,
  HTTPAPI_REQUEST_DELETE,
  HTTPAPI_REQUEST_PATCH,
  HTTPAPI_REQUEST_HEAD
}

```
Constant                    | Description                                
----------------------------|----------------
 HTTPAPI_REQUEST_GET            | 
 HTTPAPI_REQUEST_POST            | 
 HTTPAPI_REQUEST_PUT            | 
 HTTPAPI_REQUEST_DELETE            | 
 HTTPAPI_REQUEST_PATCH            | 
 HTTPAPI_REQUEST_HEAD            | 

