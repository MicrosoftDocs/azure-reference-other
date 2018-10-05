# prov_device_client.h 

Extends the Prov_Device_LL module with additional features.

## Includes

\#include <stddef.h>  
\#include <stdint.h>  
\#include "[prov_device_ll_client.h](iot-c-ref-prov-device-ll-client-h.md)"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include "[azure_prov_client/prov_transport.h](iot-c-ref-prov-transport-h.md)"  

## Detailed Description

Prov_Device is a module that extends the Prov_Device_LL module with 2 features:

* scheduling the work for the IoTHubCLient from a thread, so that the user does not need to create their own thread

* thread-safe APIs

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[Prov_Device_Create](./iot-c-ref-prov-device-client-h/prov-device-create.md)            | 
[Prov_Device_Destroy](./iot-c-ref-prov-device-client-h/prov-device-destroy.md)            | 
[Prov_Device_Register_Device](./iot-c-ref-prov-device-client-h/prov-device-register-device.md)            | 
[Prov_Device_SetOption](./iot-c-ref-prov-device-client-h/prov-device-setoption.md)            | 
[Prov_Device_GetVersionString](./iot-c-ref-prov-device-client-h/prov-device-getversionstring.md)            | 

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
PROV_DEVICE_CLIENT_INSTANCE_TYPE            | 

## Typedefs

####PROV_DEVICE_HANDLE

```C
typedef struct PROV_DEVICE_INSTANCE_TAG * PROV_DEVICE_HANDLE()

```

