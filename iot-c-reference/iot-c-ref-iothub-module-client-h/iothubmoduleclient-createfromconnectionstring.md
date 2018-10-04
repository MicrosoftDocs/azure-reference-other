# IoTHubModuleClient_CreateFromConnectionString()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_module_client.h"](../iot-c-ref-iothub-module-client-h.md)  

**[IOTHUB_MODULE_CLIENT_HANDLE](#iothub__module__client_8h_1a61259310a513ae73b31cb3c66d3f4087) [IoTHubModuleClient_CreateFromConnectionString](#iothub__module__client_8h_1a56060237dbed8445a3e0ecc27654fa71)(const char * connectionString,[IOTHUB_CLIENT_TRANSPORT_PROVIDER](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol)**

Creates a IoT Hub client for communication with an existing IoT Hub using the specified connection string parameter.

#### Parameters
* `connectionString` Pointer to a character string 

* `protocol` Function pointer for protocol implementation

Sample connection string: 
```
HostName=[IoT Hub name goes here].[IoT Hub suffix goes here, e.g., private.azure-devices-int.net];DeviceId=[Device ID goes here];SharedAccessKey=[Device key goes here];ModuleId=[Module ID goes here]
HostName=[IoT Hub name goes here].[IoT Hub suffix goes here, e.g., private.azure-devices-int.net];DeviceId=[Device ID goes here];SharedAccessSignature=SharedAccessSignature sr=[IoT Hub name goes here].[IoT Hub suffix goes here, e.g., private.azure-devices-int.net]/devices/[Device ID goes here]&sig=[SAS Token goes here]&se=[Expiry Time goes here];ModuleId=[Module ID goes here]

```

#### Returns
A non-NULL `IOTHUB_MODULE_CLIENT_HANDLE` value that is used when invoking other functions for IoT Hub client and `NULL` on failure.

