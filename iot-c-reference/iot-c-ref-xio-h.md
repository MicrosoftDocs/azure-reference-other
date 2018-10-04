# Header file xio.h 

Stub comment for brief. Please update this comment.

## Includes

\#include ["azure_c_shared_utility/optionhandler.h"](iot-c-ref-optionhandler-h.md)  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
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

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IO_SEND_RESULT_VALUES            | 
IO_OPEN_RESULT_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
XIO_HANDLE            | 
CONCRETE_IO_HANDLE            | 
ON_BYTES_RECEIVED            | 
ON_SEND_COMPLETE            | 
ON_IO_OPEN_COMPLETE            | 
ON_IO_CLOSE_COMPLETE            | 
ON_IO_ERROR            | 
IO_RETRIEVEOPTIONS            | 
IO_CREATE            | 
IO_DESTROY            | 
IO_OPEN            | 
IO_CLOSE            | 
IO_SEND            | 
IO_DOWORK            | 
IO_SETOPTION            | 

## Function documentation

#### IO_SEND_RESULTStrings 
const char * `[`IO_SEND_RESULTStrings`](#xio_8h_1a416b3c0568688eb7e120d3c125270cf8)(`[`IO_SEND_RESULT`](#xio_8h_1af7c3c4f484edf573bac242fa33ff4a27) value)`

#### IO_SEND_RESULT_FromString 
int `[`IO_SEND_RESULT_FromString`](#xio_8h_1a9b5782c5469e1ec8da90d71af8b24ceb)(const char * enumAsString,`[`IO_SEND_RESULT`](#xio_8h_1af7c3c4f484edf573bac242fa33ff4a27) * destination)`

#### IO_OPEN_RESULTStrings 
const char * `[`IO_OPEN_RESULTStrings`](#xio_8h_1ae5fd5d32cad905d7bd9f27fd6552c660)(`[`IO_OPEN_RESULT`](#xio_8h_1a650563dd951fb9c9751f510964f3f36b) value)`

#### IO_OPEN_RESULT_FromString 
int `[`IO_OPEN_RESULT_FromString`](#xio_8h_1a663203db6c2aa0154303adc72a7b8b80)(const char * enumAsString,`[`IO_OPEN_RESULT`](#xio_8h_1a650563dd951fb9c9751f510964f3f36b) * destination)`

#### xio_create 
[`XIO_HANDLE`](#xio_8h_1a214682528088ae784e94fbbe26fa4356) `[`xio_create`](#xio_8h_1a598cf4855bf187ba1e3a1829de1d67f7)(const `[`IO_INTERFACE_DESCRIPTION`](#struct_i_o___i_n_t_e_r_f_a_c_e___d_e_s_c_r_i_p_t_i_o_n) * io_interface_description,const void * io_create_parameters)`

#### xio_destroy 
void `[`xio_destroy`](#xio_8h_1acf7bf0887a6f4a203740745d27d21bb1)(`[`XIO_HANDLE`](#xio_8h_1a214682528088ae784e94fbbe26fa4356) xio)`

#### xio_open 
int `[`xio_open`](#xio_8h_1aff8b447060a2e4671fdc6ad93c5654c2)(`[`XIO_HANDLE`](#xio_8h_1a214682528088ae784e94fbbe26fa4356) xio,`[`ON_IO_OPEN_COMPLETE`](#xio_8h_1a3acca89b8b5ff3d42b3eaf0b3dbcf7ca) on_io_open_complete,void * on_io_open_complete_context,`[`ON_BYTES_RECEIVED`](#xio_8h_1a13198b46d201d067f60a82c1bf0e5780) on_bytes_received,void * on_bytes_received_context,`[`ON_IO_ERROR`](#xio_8h_1a2761e39867e9372423f77921fc5fd26d) on_io_error,void * on_io_error_context)`

#### xio_close 
int `[`xio_close`](#xio_8h_1a83d9da875cf42f4f1ce130664a9b3860)(`[`XIO_HANDLE`](#xio_8h_1a214682528088ae784e94fbbe26fa4356) xio,`[`ON_IO_CLOSE_COMPLETE`](#xio_8h_1afdff4c121fba1278335064c5686cc419) on_io_close_complete,void * callback_context)`

#### xio_send 
int `[`xio_send`](#xio_8h_1a8055217d505db388235a00b700aa1562)(`[`XIO_HANDLE`](#xio_8h_1a214682528088ae784e94fbbe26fa4356) xio,const void * buffer,size_t size,`[`ON_SEND_COMPLETE`](#xio_8h_1a9275b2e616c2abadf629ca3d94d7871f) on_send_complete,void * callback_context)`

#### xio_dowork 
void `[`xio_dowork`](#xio_8h_1ad1678d0cc44c83eb2bdc0eee0be12925)(`[`XIO_HANDLE`](#xio_8h_1a214682528088ae784e94fbbe26fa4356) xio)`

#### xio_setoption 
int `[`xio_setoption`](#xio_8h_1ab842aa9de72d9359ac059be7428c59d5)(`[`XIO_HANDLE`](#xio_8h_1a214682528088ae784e94fbbe26fa4356) xio,const char * optionName,const void * value)`

#### xio_retrieveoptions 
[`OPTIONHANDLER_HANDLE`](#optionhandler_8h_1a1989d75401220ac319c1fca9a5a2737b) `[`xio_retrieveoptions`](#xio_8h_1a42cdddeb35bf5a6d45a4a730b1b9e4a5)(`[`XIO_HANDLE`](#xio_8h_1a214682528088ae784e94fbbe26fa4356) xio)`

