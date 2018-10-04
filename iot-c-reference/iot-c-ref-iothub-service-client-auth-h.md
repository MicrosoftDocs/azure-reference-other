# Header file iothub_service_client_auth.h 

APIs that allow a user (usually a device) to create and destroy a handle for use in Service client APIs.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  

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

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IOTHUB_DEVICE_STATUS_VALUES            | 
IOTHUB_DEVICE_CONNECTION_STATE_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
IOTHUB_SERVICE_CLIENT_AUTH_HANDLE            | Handle to hide struct and use it in consequent APIs.

## Function documentation

#### IOTHUB_DEVICE_STATUSStrings 
const char * [IOTHUB_DEVICE_STATUSStrings](#iothub__service__client__auth_8h_1a65b70618c8f8fe5452c48a6d29d1d94a)([IOTHUB_DEVICE_STATUS](#iothub__service__client__auth_8h_1a3b440e97db15b4c853abad558a0f173b) value)

#### IOTHUB_DEVICE_STATUS_FromString 
int [IOTHUB_DEVICE_STATUS_FromString](#iothub__service__client__auth_8h_1ae7c2ff1c3ba0ab9a8fe69905fc517a50)(const char * enumAsString,[IOTHUB_DEVICE_STATUS](#iothub__service__client__auth_8h_1a3b440e97db15b4c853abad558a0f173b) * destination)

#### IOTHUB_DEVICE_CONNECTION_STATEStrings 
const char * [IOTHUB_DEVICE_CONNECTION_STATEStrings](#iothub__service__client__auth_8h_1aa7de753450243ee66c108ea23f631c60)([IOTHUB_DEVICE_CONNECTION_STATE](#iothub__service__client__auth_8h_1ab3a1b1002cb03e5bfca8a0e83ea0e905) value)

#### IOTHUB_DEVICE_CONNECTION_STATE_FromString 
int [IOTHUB_DEVICE_CONNECTION_STATE_FromString](#iothub__service__client__auth_8h_1a85852a98592beb36553eb399db92aaf6)(const char * enumAsString,[IOTHUB_DEVICE_CONNECTION_STATE](#iothub__service__client__auth_8h_1ab3a1b1002cb03e5bfca8a0e83ea0e905) * destination)

#### IoTHubServiceClientAuth_CreateFromConnectionString 
[IOTHUB_SERVICE_CLIENT_AUTH_HANDLE](#iothub__service__client__auth_8h_1a47d2f6357931c33108eb9fba95d8730b) [IoTHubServiceClientAuth_CreateFromConnectionString](#iothub__service__client__auth_8h_1a4f24671454a250ef6f5adaf2aa01d22e)(const char * connectionString)

#### IoTHubServiceClientAuth_Destroy 
void [IoTHubServiceClientAuth_Destroy](#iothub__service__client__auth_8h_1ad2296c94d1f35466b0bad0236c28d1da)([IOTHUB_SERVICE_CLIENT_AUTH_HANDLE](#iothub__service__client__auth_8h_1a47d2f6357931c33108eb9fba95d8730b) serviceClientHandle)

