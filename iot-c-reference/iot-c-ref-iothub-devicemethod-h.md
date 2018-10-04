# Header file iothub_devicemethod.h 

Stub comment for brief. Please update this comment.

## Includes

\#include ["iothub_service_client_auth.h"](iot-c-ref-iothub-service-client-auth-h.md)  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IOTHUB_DEVICE_METHOD_RESULTStrings](./iot-c-ref-iothub-devicemethod-h/iothub-device-method-resultstrings.md)            | 
[IOTHUB_DEVICE_METHOD_RESULT_FromString](./iot-c-ref-iothub-devicemethod-h/iothub-device-method-result-fromstring.md)            | 
[IoTHubDeviceMethod_Create](./iot-c-ref-iothub-devicemethod-h/iothubdevicemethod-create.md)            | Creates a IoT Hub Service Client DeviceMethod handle for use it in consequent APIs.
[IoTHubDeviceMethod_Destroy](./iot-c-ref-iothub-devicemethod-h/iothubdevicemethod-destroy.md)            | Disposes of resources allocated by the IoT Hub IoTHubDeviceMethod_Create.
[IoTHubDeviceMethod_Invoke](./iot-c-ref-iothub-devicemethod-h/iothubdevicemethod-invoke.md)            | Call a method on device with a given payload.
[IoTHubDeviceMethod_InvokeModule](./iot-c-ref-iothub-devicemethod-h/iothubdevicemethod-invokemodule.md)            | Call a method on device and a module with a given payload.

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IOTHUB_DEVICE_METHOD_RESULT_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
IOTHUB_SERVICE_CLIENT_DEVICE_METHOD_HANDLE            | Handle to hide struct and use it in consequent APIs.

## Function documentation

#### IOTHUB_DEVICE_METHOD_RESULTStrings 
const char * [IOTHUB_DEVICE_METHOD_RESULTStrings](#iothub__devicemethod_8h_1aabac5330bd9d43bdb14862e192a916c1)([IOTHUB_DEVICE_METHOD_RESULT](#iothub__devicemethod_8h_1a8adffbffc2f6e136f8406c5ef396602d) value)

#### IOTHUB_DEVICE_METHOD_RESULT_FromString 
int [IOTHUB_DEVICE_METHOD_RESULT_FromString](#iothub__devicemethod_8h_1a38e9aef8805699d16890d4ffa6c17760)(const char * enumAsString,[IOTHUB_DEVICE_METHOD_RESULT](#iothub__devicemethod_8h_1a8adffbffc2f6e136f8406c5ef396602d) * destination)

#### IoTHubDeviceMethod_Create 
[IOTHUB_SERVICE_CLIENT_DEVICE_METHOD_HANDLE](#iothub__devicemethod_8h_1a06b6ee10c1627d4f7463c4204490051a) [IoTHubDeviceMethod_Create](#iothub__devicemethod_8h_1a30d7823cef3cfd35ff3e2da3db9c71bf)([IOTHUB_SERVICE_CLIENT_AUTH_HANDLE](#iothub__service__client__auth_8h_1a47d2f6357931c33108eb9fba95d8730b) serviceClientHandle)

#### IoTHubDeviceMethod_Destroy 
void [IoTHubDeviceMethod_Destroy](#iothub__devicemethod_8h_1ac8ac5bbf0a587a11c8c1fe5b6b26aefd)([IOTHUB_SERVICE_CLIENT_DEVICE_METHOD_HANDLE](#iothub__devicemethod_8h_1a06b6ee10c1627d4f7463c4204490051a) serviceClientDeviceMethodHandle)

#### IoTHubDeviceMethod_Invoke 
[IOTHUB_DEVICE_METHOD_RESULT](#iothub__devicemethod_8h_1a8adffbffc2f6e136f8406c5ef396602d) [IoTHubDeviceMethod_Invoke](#iothub__devicemethod_8h_1abdfab207152397a0c843d12a0db4bbf8)([IOTHUB_SERVICE_CLIENT_DEVICE_METHOD_HANDLE](#iothub__devicemethod_8h_1a06b6ee10c1627d4f7463c4204490051a) serviceClientDeviceMethodHandle,const char * deviceId,const char * methodName,const char * methodPayload,unsigned int timeout,int * responseStatus,unsigned char ** responsePayload,size_t * responsePayloadSize)

#### IoTHubDeviceMethod_InvokeModule 
[IOTHUB_DEVICE_METHOD_RESULT](#iothub__devicemethod_8h_1a8adffbffc2f6e136f8406c5ef396602d) [IoTHubDeviceMethod_InvokeModule](#iothub__devicemethod_8h_1a310892fc47bf32878894ea21a3ca02ba)([IOTHUB_SERVICE_CLIENT_DEVICE_METHOD_HANDLE](#iothub__devicemethod_8h_1a06b6ee10c1627d4f7463c4204490051a) serviceClientDeviceMethodHandle,const char * deviceId,const char * moduleId,const char * methodName,const char * methodPayload,unsigned int timeout,int * responseStatus,unsigned char ** responsePayload,size_t * responsePayloadSize)

