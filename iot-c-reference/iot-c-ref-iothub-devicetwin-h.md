# Header file iothub_devicetwin.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/crt_abstractions.h"  
\#include ["azure_c_shared_utility/singlylinkedlist.h"](iot-c-ref-singlylinkedlist-h.md)  
\#include ["azure_c_shared_utility/map.h"](iot-c-ref-map-h.md)  
\#include <time.h>  
\#include ["iothub_service_client_auth.h"](iot-c-ref-iothub-service-client-auth-h.md)  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IOTHUB_DEVICE_TWIN_RESULTStrings](./iot-c-ref-iothub-devicetwin-h/iothub-device-twin-resultstrings.md)            | 
[IOTHUB_DEVICE_TWIN_RESULT_FromString](./iot-c-ref-iothub-devicetwin-h/iothub-device-twin-result-fromstring.md)            | 
[IoTHubDeviceTwin_Create](./iot-c-ref-iothub-devicetwin-h/iothubdevicetwin-create.md)            | Creates a IoT Hub Service Client DeviceTwin handle for use it in consequent APIs.
[IoTHubDeviceTwin_Destroy](./iot-c-ref-iothub-devicetwin-h/iothubdevicetwin-destroy.md)            | Disposes of resources allocated by the IoT Hub IoTHubDeviceTwin_Create.
[IoTHubDeviceTwin_GetTwin](./iot-c-ref-iothub-devicetwin-h/iothubdevicetwin-gettwin.md)            | Retrieves the given device's twin info.
[IoTHubDeviceTwin_UpdateTwin](./iot-c-ref-iothub-devicetwin-h/iothubdevicetwin-updatetwin.md)            | Updates (partial update) the given device's twin info.
[IoTHubDeviceTwin_GetModuleTwin](./iot-c-ref-iothub-devicetwin-h/iothubdevicetwin-getmoduletwin.md)            | Retrieves the given module's twin info.
[IoTHubDeviceTwin_UpdateModuleTwin](./iot-c-ref-iothub-devicetwin-h/iothubdevicetwin-updatemoduletwin.md)            | Updates (partial update) the given module's twin info.

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
IOTHUB_DEVICE_TWIN_RESULT_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE            | Handle to hide struct and use it in consequent APIs.

## Function documentation

#### IOTHUB_DEVICE_TWIN_RESULTStrings 
const char * `[`IOTHUB_DEVICE_TWIN_RESULTStrings`](#iothub__devicetwin_8h_1afa05a46b6691d3ee77b57157b3b4871f)(`[`IOTHUB_DEVICE_TWIN_RESULT`](#iothub__devicetwin_8h_1a525b37a828b2aca15b247cc5ca1c494b) value)`

#### IOTHUB_DEVICE_TWIN_RESULT_FromString 
int `[`IOTHUB_DEVICE_TWIN_RESULT_FromString`](#iothub__devicetwin_8h_1adef962bed2749a4338f36ee7a7758230)(const char * enumAsString,`[`IOTHUB_DEVICE_TWIN_RESULT`](#iothub__devicetwin_8h_1a525b37a828b2aca15b247cc5ca1c494b) * destination)`

#### IoTHubDeviceTwin_Create 
[`IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE`](#iothub__devicetwin_8h_1a3394032bf6208c794f399ddfd45471c3) `[`IoTHubDeviceTwin_Create`](#iothub__devicetwin_8h_1acdd0485d9a25bb95fa1d2273e5dbffe9)(`[`IOTHUB_SERVICE_CLIENT_AUTH_HANDLE`](#iothub__service__client__auth_8h_1a47d2f6357931c33108eb9fba95d8730b) serviceClientHandle)`

#### IoTHubDeviceTwin_Destroy 
void `[`IoTHubDeviceTwin_Destroy`](#iothub__devicetwin_8h_1a0c3ca65a50ec887151374a52aacd4d7a)(`[`IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE`](#iothub__devicetwin_8h_1a3394032bf6208c794f399ddfd45471c3) serviceClientDeviceTwinHandle)`

#### IoTHubDeviceTwin_GetTwin 
char * `[`IoTHubDeviceTwin_GetTwin`](#iothub__devicetwin_8h_1ad582335584a4ddc69f7dbe881dfe723c)(`[`IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE`](#iothub__devicetwin_8h_1a3394032bf6208c794f399ddfd45471c3) serviceClientDeviceTwinHandle,const char * deviceId)`

#### IoTHubDeviceTwin_UpdateTwin 
char * `[`IoTHubDeviceTwin_UpdateTwin`](#iothub__devicetwin_8h_1adabb401facb6b2c95024beb2d351c87d)(`[`IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE`](#iothub__devicetwin_8h_1a3394032bf6208c794f399ddfd45471c3) serviceClientDeviceTwinHandle,const char * deviceId,const char * deviceTwinJson)`

#### IoTHubDeviceTwin_GetModuleTwin 
char * `[`IoTHubDeviceTwin_GetModuleTwin`](#iothub__devicetwin_8h_1a262b8e9435f1e3822e8af1d86c4bbd9a)(`[`IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE`](#iothub__devicetwin_8h_1a3394032bf6208c794f399ddfd45471c3) serviceClientDeviceTwinHandle,const char * deviceId,const char * moduleId)`

#### IoTHubDeviceTwin_UpdateModuleTwin 
char * `[`IoTHubDeviceTwin_UpdateModuleTwin`](#iothub__devicetwin_8h_1ab696d0876e2cbf2698caafbc48b537c9)(`[`IOTHUB_SERVICE_CLIENT_DEVICE_TWIN_HANDLE`](#iothub__devicetwin_8h_1a3394032bf6208c794f399ddfd45471c3) serviceClientDeviceTwinHandle,const char * deviceId,const char * moduleId,const char * moduleTwinJson)`

