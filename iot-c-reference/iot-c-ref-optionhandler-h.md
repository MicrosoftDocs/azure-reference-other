# Header file optionhandler.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[OPTIONHANDLER_RESULTStrings](./iot-c-ref-optionhandler-h/optionhandler-resultstrings.md)            | 
[OPTIONHANDLER_RESULT_FromString](./iot-c-ref-optionhandler-h/optionhandler-result-fromstring.md)            | 
[OptionHandler_Create](./iot-c-ref-optionhandler-h/optionhandler-create.md)            | 
[OptionHandler_Clone](./iot-c-ref-optionhandler-h/optionhandler-clone.md)            | 
[OptionHandler_AddOption](./iot-c-ref-optionhandler-h/optionhandler-addoption.md)            | 
[OptionHandler_FeedOptions](./iot-c-ref-optionhandler-h/optionhandler-feedoptions.md)            | 
[OptionHandler_Destroy](./iot-c-ref-optionhandler-h/optionhandler-destroy.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
OPTIONHANDLER_RESULT_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
OPTIONHANDLER_HANDLE            | 
pfCloneOption            | 
pfDestroyOption            | 
pfSetOption            | 

## Function documentation

#### OPTIONHANDLER_RESULTStrings 
const char * `[`OPTIONHANDLER_RESULTStrings`](#optionhandler_8h_1a93deb984d3f8fee73fa9a19aa50e0eed)(`[`OPTIONHANDLER_RESULT`](#optionhandler_8h_1aa39865f6f7b6692ac4d724fac6c9dbbd) value)`

#### OPTIONHANDLER_RESULT_FromString 
int `[`OPTIONHANDLER_RESULT_FromString`](#optionhandler_8h_1a9ae064991edfd769f1dd8b7c6f3222a7)(const char * enumAsString,`[`OPTIONHANDLER_RESULT`](#optionhandler_8h_1aa39865f6f7b6692ac4d724fac6c9dbbd) * destination)`

#### OptionHandler_Create 
[`OPTIONHANDLER_HANDLE`](#optionhandler_8h_1a1989d75401220ac319c1fca9a5a2737b) `[`OptionHandler_Create`](#optionhandler_8h_1a6b1983fd63165d559e91335e024334d2)(`[`pfCloneOption`](#optionhandler_8h_1a7f44e24f59f430c438585334855a825e) cloneOption,`[`pfDestroyOption`](#optionhandler_8h_1aa2c29d4ec7391e4dabedff6b0b6f9388) destroyOption,`[`pfSetOption`](#optionhandler_8h_1a165fe90e9fd1a284ac5a1e2f0a90fd97) setOption)`

#### OptionHandler_Clone 
[`OPTIONHANDLER_HANDLE`](#optionhandler_8h_1a1989d75401220ac319c1fca9a5a2737b) `[`OptionHandler_Clone`](#optionhandler_8h_1a1dcf543245871a21565348a9f06eba99)(`[`OPTIONHANDLER_HANDLE`](#optionhandler_8h_1a1989d75401220ac319c1fca9a5a2737b) handler)`

#### OptionHandler_AddOption 
[`OPTIONHANDLER_RESULT`](#optionhandler_8h_1aa39865f6f7b6692ac4d724fac6c9dbbd) `[`OptionHandler_AddOption`](#optionhandler_8h_1a698bb81b93afb8f436c71e11b9a6287f)(`[`OPTIONHANDLER_HANDLE`](#optionhandler_8h_1a1989d75401220ac319c1fca9a5a2737b) handle,const char * name,const void * value)`

#### OptionHandler_FeedOptions 
[`OPTIONHANDLER_RESULT`](#optionhandler_8h_1aa39865f6f7b6692ac4d724fac6c9dbbd) `[`OptionHandler_FeedOptions`](#optionhandler_8h_1afeea10981f7e63a37cb6af40c0a1bff4)(`[`OPTIONHANDLER_HANDLE`](#optionhandler_8h_1a1989d75401220ac319c1fca9a5a2737b) handle,void * destinationHandle)`

#### OptionHandler_Destroy 
void `[`OptionHandler_Destroy`](#optionhandler_8h_1a4b32e141221e6cdfaa44ac5e0e87711f)(`[`OPTIONHANDLER_HANDLE`](#optionhandler_8h_1a1989d75401220ac319c1fca9a5a2737b) handle)`

