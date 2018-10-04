# Header file provisioning_sc_device_capabilities.h 

Stub comment for brief. Please update this comment.

## Includes

\#include <stdbool.h>  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include "parson.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[deviceCapabilities_create](./iot-c-ref-provisioning-sc-device-capabilities-h/devicecapabilities-create.md)            | Creates a Device Capabilities handle that can be used in consequent APIs, with all fields initialized to "false".
[deviceCapabilities_destroy](./iot-c-ref-provisioning-sc-device-capabilities-h/devicecapabilities-destroy.md)            | Destroys a Device Capabilities handle, freeing all associated memory. Please note that if the Device Capabilities are attached to an Enrollment, this will remove it.
[deviceCapabilities_isIotEdgeCapable](./iot-c-ref-provisioning-sc-device-capabilities-h/devicecapabilities-isiotedgecapable.md)            | 
[deviceCapabilities_setIotEdgeCapable](./iot-c-ref-provisioning-sc-device-capabilities-h/devicecapabilities-setiotedgecapable.md)            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
DEVICE_CAPABILITIES_HANDLE            | 

## Function documentation

#### deviceCapabilities_create 
[`DEVICE_CAPABILITIES_HANDLE`](#provisioning__sc__device__capabilities_8h_1af33545b05ae4501337bcfeaecce34ae4) `[`deviceCapabilities_create`](#provisioning__sc__device__capabilities_8h_1a6a6ab7129cb10af2505ecbfd11c8d602)(void)`

#### deviceCapabilities_destroy 
void `[`deviceCapabilities_destroy`](#provisioning__sc__device__capabilities_8h_1ae01cf74fe5498757d4da936901b6ac46)(`[`DEVICE_CAPABILITIES_HANDLE`](#provisioning__sc__device__capabilities_8h_1af33545b05ae4501337bcfeaecce34ae4) capabilities)`

#### deviceCapabilities_isIotEdgeCapable 
bool `[`deviceCapabilities_isIotEdgeCapable`](#provisioning__sc__device__capabilities_8h_1abe93f713071d3fff2355ea083fdd4b27)(`[`DEVICE_CAPABILITIES_HANDLE`](#provisioning__sc__device__capabilities_8h_1af33545b05ae4501337bcfeaecce34ae4) capabilities)`

#### deviceCapabilities_setIotEdgeCapable 
void `[`deviceCapabilities_setIotEdgeCapable`](#provisioning__sc__device__capabilities_8h_1a0e07bafb64b64e6f44fc04464594977d)(`[`DEVICE_CAPABILITIES_HANDLE`](#provisioning__sc__device__capabilities_8h_1af33545b05ae4501337bcfeaecce34ae4) capabilities,bool iotEdgeCapable)`

