# IoTHubModuleClient_LL_CreateFromConnectionString()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client_ll.h"](../iot-c-ref-iothub-module-client-ll-h.md)  

[`IOTHUB_MODULE_CLIENT_LL_HANDLE`](#iothub__module__client__ll_8h_1ae1a6187aacbdb56cde026ad3d228420a) `[`IoTHubModuleClient_LL_CreateFromConnectionString`](#iothub__module__client__ll_8h_1ab99ab4387fd82182d98e7231615eaf8f)(const char * connectionString,`[`IOTHUB_CLIENT_TRANSPORT_PROVIDER`](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)`

Creates a IoT Hub client for communication with an existing IoT Hub using the specified connection string parameter.

#### Parameters
* `connectionString` Pointer to a character string 

* `protocol` Function pointer for protocol implementation

Sample connection string: HostName=[IoT Hub name goes here].[IoT Hub suffix goes here, e.g., private.azure-devices-int.net];DeviceId=[Device ID goes here];SharedAccessKey=[Device key goes here];ModuleId=[Module ID goes here]

#### Returns
A non-NULL `IOTHUB_MODULE_CLIENT_LL_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

