# socketio_open()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/socketio.h"](../iot-c-ref-socketio-h.md)  

## Syntax

```C
int socketio_open(
  CONCRETE_IO_HANDLE	socket_io,
  ON_IO_OPEN_COMPLETE	on_io_open_complete,
  void *	on_io_open_complete_context,
  ON_BYTES_RECEIVED	on_bytes_received,
  void *	on_bytes_received_context,
  ON_IO_ERROR	on_io_error,
  void *	on_io_error_context
);

```

