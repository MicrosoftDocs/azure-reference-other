# Header file socketio.h 

Stub comment for brief. Please update this comment.

## Includes

\#include ["azure_c_shared_utility/xio.h"](iot-c-ref-xio-h.md)  
\#include ["azure_c_shared_utility/xlogging.h"](iot-c-ref-xlogging-h.md)  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include <stddef.h>  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[socketio_create](./iot-c-ref-socketio-h/socketio-create.md)            | 
[socketio_destroy](./iot-c-ref-socketio-h/socketio-destroy.md)            | 
[socketio_open](./iot-c-ref-socketio-h/socketio-open.md)            | 
[socketio_close](./iot-c-ref-socketio-h/socketio-close.md)            | 
[socketio_send](./iot-c-ref-socketio-h/socketio-send.md)            | 
[socketio_dowork](./iot-c-ref-socketio-h/socketio-dowork.md)            | 
[socketio_setoption](./iot-c-ref-socketio-h/socketio-setoption.md)            | 
[socketio_get_interface_description](./iot-c-ref-socketio-h/socketio-get-interface-description.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
RECEIVE_BYTES_VALUE            | 

## Function documentation

#### socketio_create 
[CONCRETE_IO_HANDLE](#xio_8h_1aa71532538adc618acbebd20396c0f83f) [socketio_create](#socketio_8h_1a754f1e909c69e38bc26f48e188d364fb)(void * io_create_parameters)

#### socketio_destroy 
void [socketio_destroy](#socketio_8h_1a44abdff0e6b7e8041f6ff2fbace0fd08)([CONCRETE_IO_HANDLE](#xio_8h_1aa71532538adc618acbebd20396c0f83f) socket_io)

#### socketio_open 
int [socketio_open](#socketio_8h_1a430bbf28303fe9f963463e4237cf0d46)([CONCRETE_IO_HANDLE](#xio_8h_1aa71532538adc618acbebd20396c0f83f) socket_io,[ON_IO_OPEN_COMPLETE](#xio_8h_1a3acca89b8b5ff3d42b3eaf0b3dbcf7ca) on_io_open_complete,void * on_io_open_complete_context,[ON_BYTES_RECEIVED](#xio_8h_1a13198b46d201d067f60a82c1bf0e5780) on_bytes_received,void * on_bytes_received_context,[ON_IO_ERROR](#xio_8h_1a2761e39867e9372423f77921fc5fd26d) on_io_error,void * on_io_error_context)

#### socketio_close 
int [socketio_close](#socketio_8h_1a8c6afc0ba62a495c58c863669b1760b6)([CONCRETE_IO_HANDLE](#xio_8h_1aa71532538adc618acbebd20396c0f83f) socket_io,[ON_IO_CLOSE_COMPLETE](#xio_8h_1afdff4c121fba1278335064c5686cc419) on_io_close_complete,void * callback_context)

#### socketio_send 
int [socketio_send](#socketio_8h_1a80656bed049dc641f7bd065be19b41a6)([CONCRETE_IO_HANDLE](#xio_8h_1aa71532538adc618acbebd20396c0f83f) socket_io,const void * buffer,size_t size,[ON_SEND_COMPLETE](#xio_8h_1a9275b2e616c2abadf629ca3d94d7871f) on_send_complete,void * callback_context)

#### socketio_dowork 
void [socketio_dowork](#socketio_8h_1a1c8be1127efc307f9e98d15fd0bd5861)([CONCRETE_IO_HANDLE](#xio_8h_1aa71532538adc618acbebd20396c0f83f) socket_io)

#### socketio_setoption 
int [socketio_setoption](#socketio_8h_1a918529271624b5b7ef98a396a254f53c)([CONCRETE_IO_HANDLE](#xio_8h_1aa71532538adc618acbebd20396c0f83f) socket_io,const char * optionName,const void * value)

#### socketio_get_interface_description 
const [IO_INTERFACE_DESCRIPTION](#struct_i_o___i_n_t_e_r_f_a_c_e___d_e_s_c_r_i_p_t_i_o_n) * [socketio_get_interface_description](#socketio_8h_1a617d3e5edaa31447c9e6051fcb2a8df1)(void)

