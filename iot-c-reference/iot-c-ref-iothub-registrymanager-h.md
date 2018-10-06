# iothub_registrymanager.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/macro_utils.h"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "azure_c_shared_utility/crt_abstractions.h"  
\#include "[azure_c_shared_utility/singlylinkedlist.h](iot-c-ref-singlylinkedlist-h.md)"  
\#include "[azure_c_shared_utility/map.h](iot-c-ref-map-h.md)"  
\#include "[iothub_service_client_auth.h](iot-c-ref-iothub-service-client-auth-h.md)"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IOTHUB_REGISTRYMANAGER_RESULTStrings](./iot-c-ref-iothub-registrymanager-h/iothub-registrymanager-resultstrings.md)            | 
[IOTHUB_REGISTRYMANAGER_RESULT_FromString](./iot-c-ref-iothub-registrymanager-h/iothub-registrymanager-result-fromstring.md)            | 
[IOTHUB_REGISTRYMANAGER_AUTH_METHODStrings](./iot-c-ref-iothub-registrymanager-h/iothub-registrymanager-auth-methodstrings.md)            | 
[IOTHUB_REGISTRYMANAGER_AUTH_METHOD_FromString](./iot-c-ref-iothub-registrymanager-h/iothub-registrymanager-auth-method-fromstring.md)            | 
[IoTHubRegistryManager_FreeDeviceExMembers](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-freedeviceexmembers.md)            | Free members of the [IOTHUB_DEVICE_EX](#undefined) structure (NOT the structure itself)
[IoTHubRegistryManager_FreeModuleMembers](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-freemodulemembers.md)            | Free members of the [IOTHUB_MODULE](#undefined) structure (NOT the structure itself)
[IoTHubRegistryManager_Create](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-create.md)            | Creates a IoT Hub Registry Manager handle for use it in consequent APIs.
[IoTHubRegistryManager_Destroy](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-destroy.md)            | Disposes of resources allocated by the IoT Hub Registry Manager.
[IoTHubRegistryManager_CreateDevice_Ex](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-createdevice-ex.md)            | Creates a device on IoT Hub.
[IoTHubRegistryManager_GetDevice_Ex](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getdevice-ex.md)            | Gets device info for a given device.
[IoTHubRegistryManager_UpdateDevice_Ex](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-updatedevice-ex.md)            | Updates a device on IoT Hub.
[IoTHubRegistryManager_DeleteDevice](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-deletedevice.md)            | Deletes a given device.
[IoTHubRegistryManager_GetStatistics](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getstatistics.md)            | Gets the registry statistic info.
[IoTHubRegistryManager_CreateModule](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-createmodule.md)            | Creates a module on IoT Hub.
[IoTHubRegistryManager_GetModule](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getmodule.md)            | Gets module info for a given module.
[IoTHubRegistryManager_UpdateModule](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-updatemodule.md)            | Updates a module on IoT Hub.
[IoTHubRegistryManager_DeleteModule](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-deletemodule.md)            | Deletes a given module.
[IoTHubRegistryManager_GetModuleList](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getmodulelist.md)            | Gets a list of modules registered on the specified device.
[IoTHubRegistryManager_CreateDevice](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-createdevice.md)            | Creates a device on IoT Hub.
[IoTHubRegistryManager_GetDevice](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getdevice.md)            | Gets device info for a given device.
[IoTHubRegistryManager_UpdateDevice](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-updatedevice.md)            | Updates a device on IoT Hub.
[IoTHubRegistryManager_GetDeviceList](./iot-c-ref-iothub-registrymanager-h/iothubregistrymanager-getdevicelist.md)            | 

## Structures

#### IOTHUB_DEVICE_EX

```C
struct IOTHUB_DEVICE_EX {
  int                                               version,
  const char *                                      deviceId,
  const char *                                      primaryKey,
  const char *                                      secondaryKey,
  const char *                                      generationId,
  const char *                                      eTag,
  [IOTHUB_DEVICE_CONNECTION_STATE](#undefined)      connectionState,
  const char *                                      connectionStateUpdatedTime,
  [IOTHUB_DEVICE_STATUS](#undefined)                status,
  const char *                                      statusReason,
  const char *                                      statusUpdatedTime,
  const char *                                      lastActivityTime,
  size_t                                            cloudToDeviceMessageCount,
  bool                                              isManaged,
  const char *                                      configuration,
  const char *                                      deviceProperties,
  const char *                                      serviceProperties,
  [IOTHUB_REGISTRYMANAGER_AUTH_METHOD](#undefined)  authMethod,
  bool                                              iotEdge_capable
};
```
Member name                 | Description                                
----------------------------|----------------
 version            | 
 deviceId            | 
 primaryKey            | 
 secondaryKey            | 
 generationId            | 
 eTag            | 
 connectionState            | 
 connectionStateUpdatedTime            | 
 status            | 
 statusReason            | 
 statusUpdatedTime            | 
 lastActivityTime            | 
 cloudToDeviceMessageCount            | 
 isManaged            | 
 configuration            | 
 deviceProperties            | 
 serviceProperties            | 
 authMethod            | 
 iotEdge_capable            | 
#### IOTHUB_REGISTRY_DEVICE_CREATE_EX

```C
struct IOTHUB_REGISTRY_DEVICE_CREATE_EX {
  int                                               version,
  const char *                                      deviceId,
  const char *                                      primaryKey,
  const char *                                      secondaryKey,
  [IOTHUB_REGISTRYMANAGER_AUTH_METHOD](#undefined)  authMethod,
  bool                                              iotEdge_capable
};
```
Member name                 | Description                                
----------------------------|----------------
 version            | 
 deviceId            | 
 primaryKey            | 
 secondaryKey            | 
 authMethod            | 
 iotEdge_capable            | 
#### IOTHUB_REGISTRY_DEVICE_UPDATE_EX

```C
struct IOTHUB_REGISTRY_DEVICE_UPDATE_EX {
  int                                               version,
  const char *                                      deviceId,
  const char *                                      primaryKey,
  const char *                                      secondaryKey,
  [IOTHUB_DEVICE_STATUS](#undefined)                status,
  [IOTHUB_REGISTRYMANAGER_AUTH_METHOD](#undefined)  authMethod,
  bool                                              iotEdge_capable
};
```
Member name                 | Description                                
----------------------------|----------------
 version            | 
 deviceId            | 
 primaryKey            | 
 secondaryKey            | 
 status            | 
 authMethod            | 
 iotEdge_capable            | 
#### IOTHUB_REGISTRY_STATISTICS

```C
struct IOTHUB_REGISTRY_STATISTICS {
  size_t  totalDeviceCount,
  size_t  enabledDeviceCount,
  size_t  disabledDeviceCount
};
```
Member name                 | Description                                
----------------------------|----------------
 totalDeviceCount            | 
 enabledDeviceCount            | 
 disabledDeviceCount            | 
#### IOTHUB_MODULE

```C
struct IOTHUB_MODULE {
  int                                               version,
  const char *                                      deviceId,
  const char *                                      primaryKey,
  const char *                                      secondaryKey,
  const char *                                      generationId,
  const char *                                      eTag,
  [IOTHUB_DEVICE_CONNECTION_STATE](#undefined)      connectionState,
  const char *                                      connectionStateUpdatedTime,
  [IOTHUB_DEVICE_STATUS](#undefined)                status,
  const char *                                      statusReason,
  const char *                                      statusUpdatedTime,
  const char *                                      lastActivityTime,
  size_t                                            cloudToDeviceMessageCount,
  bool                                              isManaged,
  const char *                                      configuration,
  const char *                                      deviceProperties,
  const char *                                      serviceProperties,
  [IOTHUB_REGISTRYMANAGER_AUTH_METHOD](#undefined)  authMethod,
  const char *                                      moduleId,
  const char *                                      managedBy
};
```
Member name                 | Description                                
----------------------------|----------------
 version            | 
 deviceId            | 
 primaryKey            | 
 secondaryKey            | 
 generationId            | 
 eTag            | 
 connectionState            | 
 connectionStateUpdatedTime            | 
 status            | 
 statusReason            | 
 statusUpdatedTime            | 
 lastActivityTime            | 
 cloudToDeviceMessageCount            | 
 isManaged            | 
 configuration            | 
 deviceProperties            | 
 serviceProperties            | 
 authMethod            | 
 moduleId            | 
 managedBy            | 
#### IOTHUB_REGISTRY_MODULE_CREATE

```C
struct IOTHUB_REGISTRY_MODULE_CREATE {
  int                                               version,
  const char *                                      deviceId,
  const char *                                      primaryKey,
  const char *                                      secondaryKey,
  [IOTHUB_REGISTRYMANAGER_AUTH_METHOD](#undefined)  authMethod,
  const char *                                      moduleId,
  const char *                                      managedBy
};
```
Member name                 | Description                                
----------------------------|----------------
 version            | 
 deviceId            | 
 primaryKey            | 
 secondaryKey            | 
 authMethod            | 
 moduleId            | 
 managedBy            | 
#### IOTHUB_REGISTRY_MODULE_UPDATE

```C
struct IOTHUB_REGISTRY_MODULE_UPDATE {
  int                                               version,
  const char *                                      deviceId,
  const char *                                      primaryKey,
  const char *                                      secondaryKey,
  [IOTHUB_DEVICE_STATUS](#undefined)                status,
  [IOTHUB_REGISTRYMANAGER_AUTH_METHOD](#undefined)  authMethod,
  const char *                                      moduleId,
  const char *                                      managedBy
};
```
Member name                 | Description                                
----------------------------|----------------
 version            | 
 deviceId            | 
 primaryKey            | 
 secondaryKey            | 
 status            | 
 authMethod            | 
 moduleId            | 
 managedBy            | 
#### IOTHUB_REGISTRYMANAGER

```C
struct IOTHUB_REGISTRYMANAGER {
  char *  hostname,
  char *  iothubName,
  char *  iothubSuffix,
  char *  sharedAccessKey,
  char *  keyName,
  char *  deviceId
};
```
Member name                 | Description                                
----------------------------|----------------
 hostname            | 
 iothubName            | 
 iothubSuffix            | 
 sharedAccessKey            | 
 keyName            | 
 deviceId            | 
#### IOTHUB_DEVICE

```C
struct IOTHUB_DEVICE {
  const char *                                      deviceId,
  const char *                                      primaryKey,
  const char *                                      secondaryKey,
  const char *                                      generationId,
  const char *                                      eTag,
  [IOTHUB_DEVICE_CONNECTION_STATE](#undefined)      connectionState,
  const char *                                      connectionStateUpdatedTime,
  [IOTHUB_DEVICE_STATUS](#undefined)                status,
  const char *                                      statusReason,
  const char *                                      statusUpdatedTime,
  const char *                                      lastActivityTime,
  size_t                                            cloudToDeviceMessageCount,
  bool                                              isManaged,
  const char *                                      configuration,
  const char *                                      deviceProperties,
  const char *                                      serviceProperties,
  [IOTHUB_REGISTRYMANAGER_AUTH_METHOD](#undefined)  authMethod
};
```
Member name                 | Description                                
----------------------------|----------------
 deviceId            | 
 primaryKey            | 
 secondaryKey            | 
 generationId            | 
 eTag            | 
 connectionState            | 
 connectionStateUpdatedTime            | 
 status            | 
 statusReason            | 
 statusUpdatedTime            | 
 lastActivityTime            | 
 cloudToDeviceMessageCount            | 
 isManaged            | 
 configuration            | 
 deviceProperties            | 
 serviceProperties            | 
 authMethod            | 
#### IOTHUB_REGISTRY_DEVICE_CREATE

```C
struct IOTHUB_REGISTRY_DEVICE_CREATE {
  const char *                                      deviceId,
  const char *                                      primaryKey,
  const char *                                      secondaryKey,
  [IOTHUB_REGISTRYMANAGER_AUTH_METHOD](#undefined)  authMethod
};
```
Member name                 | Description                                
----------------------------|----------------
 deviceId            | 
 primaryKey            | 
 secondaryKey            | 
 authMethod            | 
#### IOTHUB_REGISTRY_DEVICE_UPDATE

```C
struct IOTHUB_REGISTRY_DEVICE_UPDATE {
  const char *                                      deviceId,
  const char *                                      primaryKey,
  const char *                                      secondaryKey,
  [IOTHUB_DEVICE_STATUS](#undefined)                status,
  [IOTHUB_REGISTRYMANAGER_AUTH_METHOD](#undefined)  authMethod
};
```
Member name                 | Description                                
----------------------------|----------------
 deviceId            | 
 primaryKey            | 
 secondaryKey            | 
 status            | 
 authMethod            | 

## Macro definitions

#### IOTHUB_REGISTRYMANAGER_RESULT_VALUES

```C
#define IOTHUB_REGISTRYMANAGER_RESULT_VALUES \
 IOTHUB_REGISTRYMANAGER_OK, \
 IOTHUB_REGISTRYMANAGER_INVALID_ARG, \
 IOTHUB_REGISTRYMANAGER_ERROR, \
 IOTHUB_REGISTRYMANAGER_JSON_ERROR, \
 IOTHUB_REGISTRYMANAGER_HTTPAPI_ERROR, \
 IOTHUB_REGISTRYMANAGER_HTTP_STATUS_ERROR, \
 IOTHUB_REGISTRYMANAGER_DEVICE_EXIST, \
 IOTHUB_REGISTRYMANAGER_DEVICE_NOT_EXIST, \
 IOTHUB_REGISTRYMANAGER_CALLBACK_NOT_SET, \
 IOTHUB_REGISTRYMANAGER_INVALID_VERSION 

```

#### IOTHUB_REGISTRYMANAGER_AUTH_METHOD_VALUES

```C
#define IOTHUB_REGISTRYMANAGER_AUTH_METHOD_VALUES \
 IOTHUB_REGISTRYMANAGER_AUTH_SPK, \
 IOTHUB_REGISTRYMANAGER_AUTH_X509_THUMBPRINT, \
 IOTHUB_REGISTRYMANAGER_AUTH_X509_CERTIFICATE_AUTHORITY, \
 IOTHUB_REGISTRYMANAGER_AUTH_NONE, \
 IOTHUB_REGISTRYMANAGER_AUTH_UNKNOWN 

```

#### IOTHUB_DEVICE_EX_VERSION_1

```C
#define IOTHUB_DEVICE_EX_VERSION_1 1 

```

#### IOTHUB_REGISTRY_DEVICE_CREATE_EX_VERSION_1

```C
#define IOTHUB_REGISTRY_DEVICE_CREATE_EX_VERSION_1 1 

```

#### IOTHUB_REGISTRY_DEVICE_UPDATE_EX_VERSION_1

```C
#define IOTHUB_REGISTRY_DEVICE_UPDATE_EX_VERSION_1 1 

```

#### IOTHUB_MODULE_VERSION_1

```C
#define IOTHUB_MODULE_VERSION_1 1 

```

#### IOTHUB_REGISTRY_MODULE_CREATE_VERSION_1

```C
#define IOTHUB_REGISTRY_MODULE_CREATE_VERSION_1 1 

```

#### IOTHUB_REGISTRY_MODULE_UPDATE_VERSION_1

```C
#define IOTHUB_REGISTRY_MODULE_UPDATE_VERSION_1 1 

```

## Enumeration types

#### IOTHUB_REGISTRYMANAGER_RESULT

```C
enum IOTHUB_REGISTRYMANAGER_RESULT {
  IOTHUB_REGISTRYMANAGER_OK,
  IOTHUB_REGISTRYMANAGER_INVALID_ARG,
  IOTHUB_REGISTRYMANAGER_ERROR,
  IOTHUB_REGISTRYMANAGER_JSON_ERROR,
  IOTHUB_REGISTRYMANAGER_HTTPAPI_ERROR,
  IOTHUB_REGISTRYMANAGER_HTTP_STATUS_ERROR,
  IOTHUB_REGISTRYMANAGER_DEVICE_EXIST,
  IOTHUB_REGISTRYMANAGER_DEVICE_NOT_EXIST,
  IOTHUB_REGISTRYMANAGER_CALLBACK_NOT_SET,
  IOTHUB_REGISTRYMANAGER_INVALID_VERSION
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUB_REGISTRYMANAGER_OK            | 
 IOTHUB_REGISTRYMANAGER_INVALID_ARG            | 
 IOTHUB_REGISTRYMANAGER_ERROR            | 
 IOTHUB_REGISTRYMANAGER_JSON_ERROR            | 
 IOTHUB_REGISTRYMANAGER_HTTPAPI_ERROR            | 
 IOTHUB_REGISTRYMANAGER_HTTP_STATUS_ERROR            | 
 IOTHUB_REGISTRYMANAGER_DEVICE_EXIST            | 
 IOTHUB_REGISTRYMANAGER_DEVICE_NOT_EXIST            | 
 IOTHUB_REGISTRYMANAGER_CALLBACK_NOT_SET            | 
 IOTHUB_REGISTRYMANAGER_INVALID_VERSION            | 

#### IOTHUB_REGISTRYMANAGER_AUTH_METHOD

```C
enum IOTHUB_REGISTRYMANAGER_AUTH_METHOD {
  IOTHUB_REGISTRYMANAGER_AUTH_SPK,
  IOTHUB_REGISTRYMANAGER_AUTH_X509_THUMBPRINT,
  IOTHUB_REGISTRYMANAGER_AUTH_X509_CERTIFICATE_AUTHORITY,
  IOTHUB_REGISTRYMANAGER_AUTH_NONE,
  IOTHUB_REGISTRYMANAGER_AUTH_UNKNOWN
}

```
Constant                    | Description                                
----------------------------|----------------
 IOTHUB_REGISTRYMANAGER_AUTH_SPK            | 
 IOTHUB_REGISTRYMANAGER_AUTH_X509_THUMBPRINT            | 
 IOTHUB_REGISTRYMANAGER_AUTH_X509_CERTIFICATE_AUTHORITY            | 
 IOTHUB_REGISTRYMANAGER_AUTH_NONE            | 
 IOTHUB_REGISTRYMANAGER_AUTH_UNKNOWN            | 

## Typedef documentation

#### IOTHUB_REGISTRYMANAGER_HANDLE

Handle to hide struct and use it in consequent APIs. 

```C
typedef struct IOTHUB_REGISTRYMANAGER_TAG* IOTHUB_REGISTRYMANAGER_HANDLE;
```

