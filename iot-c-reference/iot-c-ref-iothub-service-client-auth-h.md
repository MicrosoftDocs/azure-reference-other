# iothub_service_client_auth.h 

APIs that allow a user (usually a device) to create and destroy a handle for use in Service client APIs.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  

## Detailed Description

APIs that allow a user (usually a device) to create a handle for use in Service client APIs. The create API parses the given connection string and saves the IoTHub specific authentication info in the handle. The destory API deallocate all the resources allocated in the handle.

User will store the handle and use it as input parameter in consequent APIs. When the handle is not needed anymore user responsbility to call destory to free all the resources.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IOTHUB_DEVICE_STATUSStrings](./iot-c-ref-iothub-service-client-auth-h/iothub-device-statusstrings.md)            | 
[IOTHUB_DEVICE_STATUS_FromString](./iot-c-ref-iothub-service-client-auth-h/iothub-device-status-fromstring.md)            | 
[IOTHUB_DEVICE_CONNECTION_STATEStrings](./iot-c-ref-iothub-service-client-auth-h/iothub-device-connection-statestrings.md)            | 
[IOTHUB_DEVICE_CONNECTION_STATE_FromString](./iot-c-ref-iothub-service-client-auth-h/iothub-device-connection-state-fromstring.md)            | 
[IoTHubServiceClientAuth_CreateFromConnectionString](./iot-c-ref-iothub-service-client-auth-h/iothubserviceclientauth-createfromconnectionstring.md)            | Creates a IoT Hub service client handle for use it in consequent APIs.
[IoTHubServiceClientAuth_Destroy](./iot-c-ref-iothub-service-client-auth-h/iothubserviceclientauth-destroy.md)            | Disposes of resources allocated by the IoT Hub Service Client.

## Structures

#### IOTHUB_SERVICE_CLIENT_AUTH

```C
struct IOTHUB_SERVICE_CLIENT_AUTH{
  char *  hostname,
  char *  iothubName,
  char *  iothubSuffix,
  char *  sharedAccessKey,
  char *  keyName,
  char *  deviceId
};
```

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IOTHUB_DEVICE_STATUS_VALUES            | 
IOTHUB_DEVICE_CONNECTION_STATE_VALUES            | 

## Typedefs

#### IOTHUB_SERVICE_CLIENT_AUTH_HANDLE

```C
typedef struct IOTHUB_SERVICE_CLIENT_AUTH_TAG * IOTHUB_SERVICE_CLIENT_AUTH_HANDLE;

```

Handle to hide struct and use it in consequent APIs.

