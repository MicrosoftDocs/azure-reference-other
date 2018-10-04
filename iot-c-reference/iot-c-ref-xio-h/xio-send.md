# xio_send()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/xio.h"](../iot-c-ref-xio-h.md)  

## Syntax

```C
int xio_send(
  XIO_HANDLE        	xio,
  const void *      	buffer,
  size_t            	size,
  ON_SEND_COMPLETE  	on_send_complete,
  void *            	callback_context
);

```

