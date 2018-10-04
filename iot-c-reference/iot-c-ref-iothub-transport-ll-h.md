# Header file iothub_transport_ll.h 

Stub comment for brief. Please update this comment.

## Includes

\#include <stddef.h>  
\#include <stdint.h>  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IoTHubTransport_Create](./iot-c-ref-iothub-transport-ll-h/iothubtransport-create.md)            | 
[IoTHubTransport_Destroy](./iot-c-ref-iothub-transport-ll-h/iothubtransport-destroy.md)            | 
[IoTHubTransport_GetLLTransport](./iot-c-ref-iothub-transport-ll-h/iothubtransport-getlltransport.md)            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
TRANSPORT_LL_HANDLE            | 
IOTHUB_DEVICE_HANDLE            | 
TRANSPORT_HANDLE            | 
METHOD_HANDLE            | 
TRANSPORT_PROVIDER            | 
IOTHUB_CLIENT_TRANSPORT_PROVIDER            | 

## Function documentation

#### IoTHubTransport_Create 
[TRANSPORT_HANDLE](#iothub__transport__ll_8h_1a085a6035b065e4f48f3789e428235aa4) [IoTHubTransport_Create](#iothub__transport__ll_8h_1a8bd6817c40f882f702c47dedea26b29f)([IOTHUB_CLIENT_TRANSPORT_PROVIDER](#iothub__transport__ll_8h_1a85d87807cf4e5cc48e62a292007f44cb) protocol,const char * iotHubName,const char * iotHubSuffix)

#### IoTHubTransport_Destroy 
void [IoTHubTransport_Destroy](#iothub__transport__ll_8h_1a7ce5be75000ff0ae71215535da0a1cc2)([TRANSPORT_HANDLE](#iothub__transport__ll_8h_1a085a6035b065e4f48f3789e428235aa4) transportHandle)

#### IoTHubTransport_GetLLTransport 
[TRANSPORT_LL_HANDLE](#iothub__transport__ll_8h_1aa36432c979d5d8bb6adaaa3ec2a74933) [IoTHubTransport_GetLLTransport](#iothub__transport__ll_8h_1aec0323191dbe96fac49e8c3bae08ef60)([TRANSPORT_HANDLE](#iothub__transport__ll_8h_1a085a6035b065e4f48f3789e428235aa4) transportHandle)

