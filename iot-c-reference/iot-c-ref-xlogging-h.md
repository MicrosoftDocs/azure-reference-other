# Header file xlogging.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/agenttime.h"  
\#include "azure_c_shared_utility/optimize_size.h"  
\#include <stdio.h>  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[LogBinary](./iot-c-ref-xlogging-h/logbinary.md)            | 
[xlogging_set_log_function](./iot-c-ref-xlogging-h/xlogging-set-log-function.md)            | 
[xlogging_get_log_function](./iot-c-ref-xlogging-h/xlogging-get-log-function.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
FUNC_NAME            | 
TEMP_BUFFER_SIZE            | 
MESSAGE_BUFFER_SIZE            | 
LOG_NONE            | 
LOG_LINE            | 
LOG            | 
LogInfo            | 
LogError            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
LOGGER_LOG            | 
LOGGER_LOG_GETLASTERROR            | 

## Function documentation

#### LogBinary 
void [LogBinary](#xlogging_8h_1a54c8f9b1b666bc682451103e4b2abe1a)(const char * comment,const void * data,size_t size)

#### xlogging_set_log_function 
void [xlogging_set_log_function](#xlogging_8h_1aa1fc162dc427fc428eac00f55c5cceb4)([LOGGER_LOG](#xlogging_8h_1ad2961c3df37a736d48986b4d9b12dd25) log_function)

#### xlogging_get_log_function 
[LOGGER_LOG](#xlogging_8h_1ad2961c3df37a736d48986b4d9b12dd25) [xlogging_get_log_function](#xlogging_8h_1adcf7cc5ced05579c5fe9c127c815471c)(void)

