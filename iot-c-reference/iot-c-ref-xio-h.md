# xio.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "[azure_c_shared_utility/optionhandler.h](iot-c-ref-optionhandler-h.md)"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include <stddef.h>  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IO_SEND_RESULTStrings](./iot-c-ref-xio-h/io-send-resultstrings.md)            | 
[IO_SEND_RESULT_FromString](./iot-c-ref-xio-h/io-send-result-fromstring.md)            | 
[IO_OPEN_RESULTStrings](./iot-c-ref-xio-h/io-open-resultstrings.md)            | 
[IO_OPEN_RESULT_FromString](./iot-c-ref-xio-h/io-open-result-fromstring.md)            | 
[xio_create](./iot-c-ref-xio-h/xio-create.md)            | 
[xio_destroy](./iot-c-ref-xio-h/xio-destroy.md)            | 
[xio_open](./iot-c-ref-xio-h/xio-open.md)            | 
[xio_close](./iot-c-ref-xio-h/xio-close.md)            | 
[xio_send](./iot-c-ref-xio-h/xio-send.md)            | 
[xio_dowork](./iot-c-ref-xio-h/xio-dowork.md)            | 
[xio_setoption](./iot-c-ref-xio-h/xio-setoption.md)            | 
[xio_retrieveoptions](./iot-c-ref-xio-h/xio-retrieveoptions.md)            | 

## Structures

#### IO_INTERFACE_DESCRIPTION

```C
struct IO_INTERFACE_DESCRIPTION {
  [IO_RETRIEVEOPTIONS](#undefined)  concrete_io_retrieveoptions,
  [IO_CREATE](#undefined)           concrete_io_create,
  [IO_DESTROY](#undefined)          concrete_io_destroy,
  [IO_OPEN](#undefined)             concrete_io_open,
  [IO_CLOSE](#undefined)            concrete_io_close,
  [IO_SEND](#undefined)             concrete_io_send,
  [IO_DOWORK](#undefined)           concrete_io_dowork,
  [IO_SETOPTION](#undefined)        concrete_io_setoption
};
```
Member name                 | Description                                
----------------------------|----------------
 concrete_io_retrieveoptions            | 
 concrete_io_create            | 
 concrete_io_destroy            | 
 concrete_io_open            | 
 concrete_io_close            | 
 concrete_io_send            | 
 concrete_io_dowork            | 
 concrete_io_setoption            | 

## Macro definitions

#### IO_SEND_RESULT_VALUES

```C
#define IO_SEND_RESULT_VALUES \
 IO_SEND_OK, \
 IO_SEND_ERROR, \
 IO_SEND_CANCELLED 

```

#### IO_OPEN_RESULT_VALUES

```C
#define IO_OPEN_RESULT_VALUES \
 IO_OPEN_OK, \
 IO_OPEN_ERROR, \
 IO_OPEN_CANCELLED 

```

## Enumeration types

#### IO_SEND_RESULT

```C
enum IO_SEND_RESULT {
  IO_SEND_OK,
  IO_SEND_ERROR,
  IO_SEND_CANCELLED
}

```
Constant                    | Description                                
----------------------------|----------------
 IO_SEND_OK            | 
 IO_SEND_ERROR            | 
 IO_SEND_CANCELLED            | 

#### IO_OPEN_RESULT

```C
enum IO_OPEN_RESULT {
  IO_OPEN_OK,
  IO_OPEN_ERROR,
  IO_OPEN_CANCELLED
}

```
Constant                    | Description                                
----------------------------|----------------
 IO_OPEN_OK            | 
 IO_OPEN_ERROR            | 
 IO_OPEN_CANCELLED            | 

