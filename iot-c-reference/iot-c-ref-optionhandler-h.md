# optionhandler.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  

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

####OPTIONHANDLER_HANDLE
typedef struct OPTIONHANDLER_HANDLE_DATA_TAG * OPTIONHANDLER_HANDLE()

####pfCloneOption
typedef void *(* pfCloneOption()

####pfDestroyOption
typedef void(* pfDestroyOption()

####pfSetOption
typedef int(* pfSetOption()

