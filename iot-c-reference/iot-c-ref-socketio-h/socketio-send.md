# socketio_send()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/socketio.h"](../iot-c-ref-socketio-h.md)  

## Syntax

```C
int socketio_send(
  CONCRETE_IO_HANDLE  	socket_io,
  const void *        	buffer,
  size_t              	size,
  ON_SEND_COMPLETE    	on_send_complete,
  void *              	callback_context
);

```

