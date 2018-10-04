# Header file threadapi.h 

This module implements support for creating new threads, terminating threads and sleeping threads.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  

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

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
THREADAPI_RESULT_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
THREAD_START_FUNC            | 
THREAD_HANDLE            | 

## Function documentation

#### THREADAPI_RESULTStrings 
const char * `[`THREADAPI_RESULTStrings`](#threadapi_8h_1a140b3ad0a5060e2209508ee2c21e1f8f)(`[`THREADAPI_RESULT`](#threadapi_8h_1a040c14bc535115c79e2f9daa57d268bd) value)`

#### THREADAPI_RESULT_FromString 
int `[`THREADAPI_RESULT_FromString`](#threadapi_8h_1a541840c0917f83cca53e4ffd7e3a7589)(const char * enumAsString,`[`THREADAPI_RESULT`](#threadapi_8h_1a040c14bc535115c79e2f9daa57d268bd) * destination)`

#### ThreadAPI_Create 
[`THREADAPI_RESULT`](#threadapi_8h_1a040c14bc535115c79e2f9daa57d268bd) `[`ThreadAPI_Create`](#threadapi_8h_1aed50c815f4090261c06968bb90644b50)(`[`THREAD_HANDLE`](#threadapi_8h_1a51f9e04bbea1ebd9fd7281a2f2a4fbf3) * threadHandle,`[`THREAD_START_FUNC`](#threadapi_8h_1a4723071f401ed47e83b73be265a71d4f) func,void * arg)`

#### ThreadAPI_Join 
[`THREADAPI_RESULT`](#threadapi_8h_1a040c14bc535115c79e2f9daa57d268bd) `[`ThreadAPI_Join`](#threadapi_8h_1aa80bce4748cbe10f4b726f2ea3168609)(`[`THREAD_HANDLE`](#threadapi_8h_1a51f9e04bbea1ebd9fd7281a2f2a4fbf3) threadHandle,int * res)`

#### ThreadAPI_Exit 
void `[`ThreadAPI_Exit`](#threadapi_8h_1a304fd6867f922d6321f36569d1769d04)(int res)`

#### ThreadAPI_Sleep 
void `[`ThreadAPI_Sleep`](#threadapi_8h_1a9ce3ec671e3aa3ca28a3e93c514dac56)(unsigned int milliseconds)`

