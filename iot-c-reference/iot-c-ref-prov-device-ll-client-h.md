# Header file prov_device_ll_client.h 

Stub comment for brief. Please update this comment.

## Includes

\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include ["azure_prov_client/prov_transport.h"](iot-c-ref-prov-transport-h.md)  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[PROV_DEVICE_RESULTStrings](./iot-c-ref-prov-device-ll-client-h/prov-device-resultstrings.md)            | 
[PROV_DEVICE_RESULT_FromString](./iot-c-ref-prov-device-ll-client-h/prov-device-result-fromstring.md)            | 
[PROV_DEVICE_REG_STATUSStrings](./iot-c-ref-prov-device-ll-client-h/prov-device-reg-statusstrings.md)            | 
[PROV_DEVICE_REG_STATUS_FromString](./iot-c-ref-prov-device-ll-client-h/prov-device-reg-status-fromstring.md)            | 
[Prov_Device_LL_Create](./iot-c-ref-prov-device-ll-client-h/prov-device-ll-create.md)            | Creates a Provisioning Client for communications with the Device Provisioning Client Service.
[Prov_Device_LL_Destroy](./iot-c-ref-prov-device-ll-client-h/prov-device-ll-destroy.md)            | Disposes of resources allocated by the provisioning Client.
[Prov_Device_LL_Register_Device](./iot-c-ref-prov-device-ll-client-h/prov-device-ll-register-device.md)            | Asynchronous call initiates the registration of a device.
[Prov_Device_LL_DoWork](./iot-c-ref-prov-device-ll-client-h/prov-device-ll-dowork.md)            | Api to be called by user when work (registering device) can be done.
[Prov_Device_LL_SetOption](./iot-c-ref-prov-device-ll-client-h/prov-device-ll-setoption.md)            | API sets a runtime option identified by parameter optionName to a value pointed to by value.
[Prov_Device_LL_GetVersionString](./iot-c-ref-prov-device-ll-client-h/prov-device-ll-getversionstring.md)            | API to get the version of the provisioning client.

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
PROV_DEVICE_RESULT_VALUE            | 
PROV_DEVICE_REG_STATUS_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
PROV_DEVICE_LL_HANDLE            | 
PROV_DEVICE_CLIENT_REGISTER_DEVICE_CALLBACK            | 
PROV_DEVICE_CLIENT_REGISTER_STATUS_CALLBACK            | 
PROV_DEVICE_TRANSPORT_PROVIDER_FUNCTION            | 

