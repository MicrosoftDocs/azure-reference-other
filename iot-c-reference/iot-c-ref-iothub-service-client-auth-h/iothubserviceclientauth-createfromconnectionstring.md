# IoTHubServiceClientAuth_CreateFromConnectionString()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_service_client_auth.h"](../iot-c-ref-iothub-service-client-auth-h.md)  

**[IOTHUB_SERVICE_CLIENT_AUTH_HANDLE](#iothub__service__client__auth_8h_1a47d2f6357931c33108eb9fba95d8730b) [IoTHubServiceClientAuth_CreateFromConnectionString](#iothub__service__client__auth_8h_1a4f24671454a250ef6f5adaf2aa01d22e)(const char * connectionString)**

Creates a IoT Hub service client handle for use it in consequent APIs.

#### Parameters
* `connectionString` Pointer to a character string

Sample connection string: 
```
HostName=[IoT Hub name goes here].[IoT Hub suffix goes here, e.g., private.azure-devices-int.net];SharedAccessKeyName=[Shared Access Key Name goes here];SharedAccessKey=[Shared Access key goes here];

```

#### Returns
A non-NULL `IOTHUB_SERVICE_CLIENT_AUTH_HANDLE` value that is used when invoking other functions for IoT Hub Service Client and `NULL` on failure.

