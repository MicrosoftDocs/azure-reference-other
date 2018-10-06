# iothub_devicemethod.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "[iothub_service_client_auth.h](iot-c-ref-iothub-service-client-auth-h.md)"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  

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

## Macro definitions

#### IOTHUB_DEVICE_METHOD_RESULT_VALUES

```C
#define IOTHUB_DEVICE_METHOD_RESULT_VALUES \
 IOTHUB_DEVICE_METHOD_OK, \
 IOTHUB_DEVICE_METHOD_INVALID_ARG, \
 IOTHUB_DEVICE_METHOD_ERROR, \
 IOTHUB_DEVICE_METHOD_HTTPAPI_ERROR 

```

## Enumeration types

#### IOTHUB_DEVICE_METHOD_RESULT

```C
enum IOTHUB_DEVICE_METHOD_RESULT {
  IOTHUB_DEVICE_METHOD_OK,
  IOTHUB_DEVICE_METHOD_INVALID_ARG,
  IOTHUB_DEVICE_METHOD_ERROR,
  IOTHUB_DEVICE_METHOD_HTTPAPI_ERROR
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUB_DEVICE_METHOD_OK            | 
 IOTHUB_DEVICE_METHOD_INVALID_ARG            | 
 IOTHUB_DEVICE_METHOD_ERROR            | 
 IOTHUB_DEVICE_METHOD_HTTPAPI_ERROR            | 

## Typedef documentation

#### IOTHUB_SERVICE_CLIENT_DEVICE_METHOD_HANDLE

Handle to hide struct and use it in consequent APIs. 

```C
typedef struct IOTHUB_SERVICE_CLIENT_DEVICE_METHOD_TAG* IOTHUB_SERVICE_CLIENT_DEVICE_METHOD_HANDLE;
```

