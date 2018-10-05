# IoTHubMessage_GetByteArray()

\#include "[azure-iot-sdk-c/iothub_client/inc/iothub_message.h](../iot-c-ref-iothub-message-h.md)"  

## Syntax

```C
IOTHUB_MESSAGE_RESULT IoTHubMessage_GetByteArray(
  IOTHUB_MESSAGE_HANDLE   iotHubMessageHandle,
  const unsigned char **  buffer,
  size_t *                size
);
```

Fetches a pointer and size for the data associated with the IoT hub message handle. If the content type of the message is not `IOTHUBMESSAGE_BYTEARRAY` then the function returns `IOTHUB_MESSAGE_INVALID_ARG`.

## Parameters
* `iotHubMessageHandle`Handle to the message. 

* `buffer`Pointer to the memory location where the pointer to the buffer will be written. 

* `size`The size of the buffer will be written to this address.

## Returns
Returns IOTHUB_MESSAGE_OK if the byte array was fetched successfully or an error code otherwise.

