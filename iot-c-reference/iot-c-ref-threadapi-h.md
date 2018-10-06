# threadapi.h 

This module implements support for creating new threads, terminating threads and sleeping threads.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  

## Detailed Description

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[THREADAPI_RESULTStrings](./iot-c-ref-threadapi-h/threadapi-resultstrings.md)            | 
[THREADAPI_RESULT_FromString](./iot-c-ref-threadapi-h/threadapi-result-fromstring.md)            | 
[ThreadAPI_Create](./iot-c-ref-threadapi-h/threadapi-create.md)            | Creates a thread with the entry point specified by the `func` argument.
[ThreadAPI_Join](./iot-c-ref-threadapi-h/threadapi-join.md)            | Blocks the calling thread by waiting on the thread identified by the `threadHandle` argument to complete.
[ThreadAPI_Exit](./iot-c-ref-threadapi-h/threadapi-exit.md)            | This function is called by a thread when the thread exits.
[ThreadAPI_Sleep](./iot-c-ref-threadapi-h/threadapi-sleep.md)            | Sleeps the current thread for the given number of milliseconds.

## Macro definitions

#### THREADAPI_RESULT_VALUES

```C
#define THREADAPI_RESULT_VALUES \
 THREADAPI_OK, \
 THREADAPI_INVALID_ARG, \
 THREADAPI_NO_MEMORY, \
 THREADAPI_ERROR 

```

## Enumeration types

#### THREADAPI_RESULT

Enumeration specifying the possible return values for the APIs in this module. 

```C
enum THREADAPI_RESULT {
  THREADAPI_OK,
  THREADAPI_INVALID_ARG,
  THREADAPI_NO_MEMORY,
  THREADAPI_ERROR
}

```
Constant                    | Description                                
----------------------------|----------------
 THREADAPI_OK            | 
 THREADAPI_INVALID_ARG            | 
 THREADAPI_NO_MEMORY            | 
 THREADAPI_ERROR            | 

