# iothub_deviceconfiguration.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/crt_abstractions.h"  
\#include "[azure_c_shared_utility/singlylinkedlist.h](iot-c-ref-singlylinkedlist-h.md)"  
\#include <time.h>  
\#include "[iothub_service_client_auth.h](iot-c-ref-iothub-service-client-auth-h.md)"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[IOTHUB_DEVICE_CONFIGURATION_RESULTStrings](./iot-c-ref-iothub-deviceconfiguration-h/iothub-device-configuration-resultstrings.md)            | 
[IOTHUB_DEVICE_CONFIGURATION_RESULT_FromString](./iot-c-ref-iothub-deviceconfiguration-h/iothub-device-configuration-result-fromstring.md)            | 
[IOTHUB_DEVICECONFIGURATION_REQUEST_MODEStrings](./iot-c-ref-iothub-deviceconfiguration-h/iothub-deviceconfiguration-request-modestrings.md)            | 
[IOTHUB_DEVICECONFIGURATION_REQUEST_MODE_FromString](./iot-c-ref-iothub-deviceconfiguration-h/iothub-deviceconfiguration-request-mode-fromstring.md)            | 
[IoTHubDeviceConfiguration_Create](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-create.md)            | Creates a IoT Hub Service Client DeviceConfiguration handle for use it in consequent APIs.
[IoTHubDeviceConfiguration_Destroy](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-destroy.md)            | Disposes of resources allocated by the IoT Hub IoTHubDeviceConfiguration_Create.
[IoTHubDeviceConfiguration_GetConfigurations](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-getconfigurations.md)            | Retrieves the Configuration info for multiple configurations from IoT Hub.
[IoTHubDeviceConfiguration_GetConfiguration](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-getconfiguration.md)            | Retrieves the Configuration info for specified configurationId from IoT Hub.
[IoTHubDeviceConfiguration_AddConfiguration](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-addconfiguration.md)            | Adds the Configuration info to IoT Hub.
[IoTHubDeviceConfiguration_UpdateConfiguration](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-updateconfiguration.md)            | Updates the given Configuration in IoT Hub.
[IoTHubDeviceConfiguration_DeleteConfiguration](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-deleteconfiguration.md)            | Deletes the given Configuration from IoT Hub.
[IoTHubDeviceConfiguration_ApplyConfigurationContentToDeviceOrModule](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-applyconfigurationcontenttodeviceormodule.md)            | Deletes the given Configuration from IoT Hub.
[IoTHubDeviceConfiguration_FreeConfigurationMembers](./iot-c-ref-iothub-deviceconfiguration-h/iothubdeviceconfiguration-freeconfigurationmembers.md)            | Free members of the [IOTHUB_DEVICE_CONFIGURATION](iot-c-ref-iothub-deviceconfiguration-h.md#iothub_device_configuration) structure (NOT the structure itself)

## Structures

#### IOTHUB_DEVICE_CONFIGURATION_CONTENT

```C
struct IOTHUB_DEVICE_CONFIGURATION_CONTENT {
  const char *  deviceContent,
  const char *  modulesContent
};
```
Member name                 | Description                                
----------------------------|----------------
 deviceContent            | 
 modulesContent            | 
#### IOTHUB_DEVICE_CONFIGURATION_METRICS_RESULT

```C
struct IOTHUB_DEVICE_CONFIGURATION_METRICS_RESULT {
  size_t         numQueries,
  const char **  queryNames,
  double *       results
};
```
Member name                 | Description                                
----------------------------|----------------
 numQueries            | 
 queryNames            | 
 results            | 
#### IOTHUB_DEVICE_CONFIGURATION_METRICS_DEFINITION

```C
struct IOTHUB_DEVICE_CONFIGURATION_METRICS_DEFINITION {
  size_t         numQueries,
  const char **  queryNames,
  const char **  queryStrings
};
```
Member name                 | Description                                
----------------------------|----------------
 numQueries            | 
 queryNames            | 
 queryStrings            | 
#### IOTHUB_DEVICE_CONFIGURATION_LABELS

```C
struct IOTHUB_DEVICE_CONFIGURATION_LABELS {
  size_t         numLabels,
  const char **  labelNames,
  const char **  labelValues
};
```
Member name                 | Description                                
----------------------------|----------------
 numLabels            | 
 labelNames            | 
 labelValues            | 
#### IOTHUB_DEVICE_CONFIGURATION

```C
struct IOTHUB_DEVICE_CONFIGURATION {
  int                                             version,
  const char *                                    schemaVersion,
  const char *                                    configurationId,
  const char *                                    targetCondition,
  const char *                                    eTag,
  const char *                                    createdTimeUtc,
  const char *                                    lastUpdatedTimeUtc,
  int                                             priority,
  IOTHUB_DEVICE_CONFIGURATION_CONTENT             content,
  IOTHUB_DEVICE_CONFIGURATION_LABELS              labels,
  IOTHUB_DEVICE_CONFIGURATION_METRICS_RESULT      systemMetricsResult,
  IOTHUB_DEVICE_CONFIGURATION_METRICS_DEFINITION  systemMetricsDefinition,
  IOTHUB_DEVICE_CONFIGURATION_METRICS_RESULT      metricResult,
  IOTHUB_DEVICE_CONFIGURATION_METRICS_DEFINITION  metricsDefinition
};
```
Member name                 | Description                                
----------------------------|----------------
 version            | 
 schemaVersion            | 
 configurationId            | 
 targetCondition            | 
 eTag            | 
 createdTimeUtc            | 
 lastUpdatedTimeUtc            | 
 priority            | 
 content            | 
 labels            | 
 systemMetricsResult            | 
 systemMetricsDefinition            | 
 metricResult            | 
 metricsDefinition            | 
#### IOTHUB_DEVICE_CONFIGURATION_ADD

```C
struct IOTHUB_DEVICE_CONFIGURATION_ADD {
  int                                             version,
  const char *                                    configurationId,
  const char *                                    targetCondition,
  int                                             priority,
  IOTHUB_DEVICE_CONFIGURATION_CONTENT             content,
  IOTHUB_DEVICE_CONFIGURATION_LABELS              labels,
  IOTHUB_DEVICE_CONFIGURATION_METRICS_DEFINITION  metrics
};
```
Member name                 | Description                                
----------------------------|----------------
 version            | 
 configurationId            | 
 targetCondition            | 
 priority            | 
 content            | 
 labels            | 
 metrics            | 

## Macro definitions

#### IOTHUB_DEVICE_CONFIGURATION_RESULT_VALUES

```C
#define IOTHUB_DEVICE_CONFIGURATION_RESULT_VALUES \
        IOTHUB_DEVICE_CONFIGURATION_OK, \
        IOTHUB_DEVICE_CONFIGURATION_INVALID_ARG, \
        IOTHUB_DEVICE_CONFIGURATION_ERROR, \
        IOTHUB_DEVICE_CONFIGURATION_HTTPAPI_ERROR, \
        IOTHUB_DEVICE_CONFIGURATION_JSON_ERROR, \
        IOTHUB_DEVICE_CONFIGURATION_OUT_OF_MEMORY_ERROR, \
        IOTHUB_DEVICE_CONFIGURATION_CONFIGURATION_NOT_EXIST, \
        IOTHUB_DEVICE_CONFIGURATION_CONFIGURATION_EXIST 
```

#### IOTHUB_DEVICECONFIGURATION_REQUEST_MODE_VALUES

```C
#define IOTHUB_DEVICECONFIGURATION_REQUEST_MODE_VALUES \
        IOTHUB_DEVICECONFIGURATION_REQUEST_GET_LIST, \
        IOTHUB_DEVICECONFIGURATION_REQUEST_GET, \
        IOTHUB_DEVICECONFIGURATION_REQUEST_ADD, \
        IOTHUB_DEVICECONFIGURATION_REQUEST_UPDATE, \
        IOTHUB_DEVICECONFIGURATION_REQUEST_DELETE, \
        IOTHUB_DEVICECONFIGURATION_REQUEST_APPLY_CONFIGURATION_CONTENT 
```

#### IOTHUB_DEVICE_CONFIGURATION_SCHEMA_VERSION_1

```C
#define IOTHUB_DEVICE_CONFIGURATION_SCHEMA_VERSION_1  "1.0" 
```

#### IOTHUB_DEVICE_CONFIGURATION_VERSION_1

```C
#define IOTHUB_DEVICE_CONFIGURATION_VERSION_1  1 
```

#### IOTHUB_DEVICE_CONFIGURATION_ADD_VERSION_1

```C
#define IOTHUB_DEVICE_CONFIGURATION_ADD_VERSION_1  1 
```

## Enumeration types

#### IOTHUB_DEVICE_CONFIGURATION_RESULT

```C
enum IOTHUB_DEVICE_CONFIGURATION_RESULT {
  IOTHUB_DEVICE_CONFIGURATION_OK,
  IOTHUB_DEVICE_CONFIGURATION_INVALID_ARG,
  IOTHUB_DEVICE_CONFIGURATION_ERROR,
  IOTHUB_DEVICE_CONFIGURATION_HTTPAPI_ERROR,
  IOTHUB_DEVICE_CONFIGURATION_JSON_ERROR,
  IOTHUB_DEVICE_CONFIGURATION_OUT_OF_MEMORY_ERROR,
  IOTHUB_DEVICE_CONFIGURATION_CONFIGURATION_NOT_EXIST,
  IOTHUB_DEVICE_CONFIGURATION_CONFIGURATION_EXIST
}
```

#### IOTHUB_DEVICECONFIGURATION_REQUEST_MODE

```C
enum IOTHUB_DEVICECONFIGURATION_REQUEST_MODE {
  IOTHUB_DEVICECONFIGURATION_REQUEST_GET_LIST,
  IOTHUB_DEVICECONFIGURATION_REQUEST_GET,
  IOTHUB_DEVICECONFIGURATION_REQUEST_ADD,
  IOTHUB_DEVICECONFIGURATION_REQUEST_UPDATE,
  IOTHUB_DEVICECONFIGURATION_REQUEST_DELETE,
  IOTHUB_DEVICECONFIGURATION_REQUEST_APPLY_CONFIGURATION_CONTENT
}
```

## Type definitions

#### IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE

Handle to hide struct and use it in consequent APIs. 

```C
typedef struct IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_TAG* IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE;
```

