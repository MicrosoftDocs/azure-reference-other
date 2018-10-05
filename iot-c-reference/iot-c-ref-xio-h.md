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

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IO_INTERFACE_DESCRIPTION](./iot-c-ref-xio-h/io-interface-description.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IO_SEND_RESULT_VALUES            | 
IO_OPEN_RESULT_VALUES            | 

## Typedefs

####XIO_HANDLE
typedef struct XIO_INSTANCE_TAG * XIO_HANDLE()

####CONCRETE_IO_HANDLE
typedef void * CONCRETE_IO_HANDLE()

####ON_BYTES_RECEIVED
typedef void(* ON_BYTES_RECEIVED()

####ON_SEND_COMPLETE
typedef void(* ON_SEND_COMPLETE()

####ON_IO_OPEN_COMPLETE
typedef void(* ON_IO_OPEN_COMPLETE()

####ON_IO_CLOSE_COMPLETE
typedef void(* ON_IO_CLOSE_COMPLETE()

####ON_IO_ERROR
typedef void(* ON_IO_ERROR()

####IO_RETRIEVEOPTIONS
typedef (* IO_RETRIEVEOPTIONS()

####IO_CREATE
typedef (* IO_CREATE()

####IO_DESTROY
typedef void(* IO_DESTROY()

####IO_OPEN
typedef int(* IO_OPEN()

####IO_CLOSE
typedef int(* IO_CLOSE()

####IO_SEND
typedef int(* IO_SEND()

####IO_DOWORK
typedef void(* IO_DOWORK()

####IO_SETOPTION
typedef int(* IO_SETOPTION()

