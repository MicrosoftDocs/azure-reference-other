# socketio.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "[azure_c_shared_utility/xio.h](iot-c-ref-xio-h.md)"  
\#include "[azure_c_shared_utility/xlogging.h](iot-c-ref-xlogging-h.md)"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
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

## Structures

#### SOCKETIO_CONFIG

```C
struct SOCKETIO_CONFIG {
  const char *  hostname,
  int           port,
  void *        accepted_socket
};
```
Member name                 | Description                                
----------------------------|----------------
 hostname            | 
 port            | 
 accepted_socket            | 

## Macro definitions

#### RECEIVE_BYTES_VALUE

```C
#define RECEIVE_BYTES_VALUE 64 

```

