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
  IO_RETRIEVEOPTIONS  concrete_io_retrieveoptions,
  IO_CREATE           concrete_io_create,
  IO_DESTROY          concrete_io_destroy,
  IO_OPEN             concrete_io_open,
  IO_CLOSE            concrete_io_close,
  IO_SEND             concrete_io_send,
  IO_DOWORK           concrete_io_dowork,
  IO_SETOPTION        concrete_io_setoption
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

## Type definitions

#### XIO_HANDLE

```C
typedef struct XIO_INSTANCE_TAG* XIO_HANDLE;
```

#### CONCRETE_IO_HANDLE

```C
typedef void* CONCRETE_IO_HANDLE;
```

#### ON_BYTES_RECEIVED

```C
typedef void(* ON_BYTES_RECEIVED) (void *context, const unsigned char *buffer, size_t size);
```

#### ON_SEND_COMPLETE

```C
typedef void(* ON_SEND_COMPLETE) (void *context, IO_SEND_RESULT send_result);
```

#### ON_IO_OPEN_COMPLETE

```C
typedef void(* ON_IO_OPEN_COMPLETE) (void *context, IO_OPEN_RESULT open_result);
```

#### ON_IO_CLOSE_COMPLETE

```C
typedef void(* ON_IO_CLOSE_COMPLETE) (void *context);
```

#### ON_IO_ERROR

```C
typedef void(* ON_IO_ERROR) (void *context);
```

#### IO_RETRIEVEOPTIONS

```C
typedef OPTIONHANDLER_HANDLE(* IO_RETRIEVEOPTIONS) (CONCRETE_IO_HANDLE concrete_io);
```

#### IO_CREATE

```C
typedef CONCRETE_IO_HANDLE(* IO_CREATE) (void *io_create_parameters);
```

#### IO_DESTROY

```C
typedef void(* IO_DESTROY) (CONCRETE_IO_HANDLE concrete_io);
```

#### IO_OPEN

```C
typedef int(* IO_OPEN) (CONCRETE_IO_HANDLE concrete_io, ON_IO_OPEN_COMPLETE on_io_open_complete, void *on_io_open_complete_context, ON_BYTES_RECEIVED on_bytes_received, void *on_bytes_received_context, ON_IO_ERROR on_io_error, void *on_io_error_context);
```

#### IO_CLOSE

```C
typedef int(* IO_CLOSE) (CONCRETE_IO_HANDLE concrete_io, ON_IO_CLOSE_COMPLETE on_io_close_complete, void *callback_context);
```

#### IO_SEND

```C
typedef int(* IO_SEND) (CONCRETE_IO_HANDLE concrete_io, const void *buffer, size_t size, ON_SEND_COMPLETE on_send_complete, void *callback_context);
```

#### IO_DOWORK

```C
typedef void(* IO_DOWORK) (CONCRETE_IO_HANDLE concrete_io);
```

#### IO_SETOPTION

```C
typedef int(* IO_SETOPTION) (CONCRETE_IO_HANDLE concrete_io, const char *optionName, const void *value);
```

