# xlogging.h 

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

## Macro definitions

#### FUNC_NAME

```C
#define FUNC_NAME  __func__ 
```

#### TEMP_BUFFER_SIZE

```C
#define TEMP_BUFFER_SIZE  1024 
```

#### MESSAGE_BUFFER_SIZE

```C
#define MESSAGE_BUFFER_SIZE  260 
```

#### LOG_NONE

```C
#define LOG_NONE  0x00 
```

#### LOG_LINE

```C
#define LOG_LINE  0x01 
```

#### LOG

```C
#define LOG \
        LOGGER_LOG, \
        xlogging_get_log_function, \
        FUNC_NAME 
```

#### LogInfo

```C
#define LogInfo \
        LOG, \
        AZ_LOG_INFO, \
        LOG_LINE 
```

#### LogError

```C
#define LogError \
        LOG, \
        AZ_LOG_ERROR, \
        LOG_LINE 
```

## Enumeration types

#### LOG_CATEGORY

```C
enum LOG_CATEGORY {
  AZ_LOG_ERROR,
  AZ_LOG_INFO,
  AZ_LOG_TRACE
}
```

## Type definitions

#### LOGGER_LOG

```C
typedef void(* LOGGER_LOG) (
  LOG_CATEGORY log_category,
   const char *file,
   const char *func,
   int line,
   unsigned int options,
   const char *format,
  ...
);
```

#### LOGGER_LOG_GETLASTERROR

```C
typedef void(* LOGGER_LOG_GETLASTERROR) (
  const char *file,
   const char *func,
   int line,
   const char *format,
  ...
);
```

