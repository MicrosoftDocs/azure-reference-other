# iothub_devicetwin.h 

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

