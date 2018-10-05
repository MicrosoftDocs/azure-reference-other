# xio_open()

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/xio.h](../iot-c-ref-xio-h.md)"  

## Syntax

```C
int xio_open(
  XIO_HANDLE           xio,
  ON_IO_OPEN_COMPLETE  on_io_open_complete,
  void *               on_io_open_complete_context,
  ON_BYTES_RECEIVED    on_bytes_received,
  void *               on_bytes_received_context,
  ON_IO_ERROR          on_io_error,
  void *               on_io_error_context);
```

