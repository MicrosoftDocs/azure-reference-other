# IoTHubRegistryManager_GetStatistics()

Gets the registry statistic info.

## Syntax

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  
```C
IOTHUB_REGISTRYMANAGER_RESULT IoTHubRegistryManager_GetStatistics(
  IOTHUB_REGISTRYMANAGER_HANDLE  registryManagerHandle,
  IOTHUB_REGISTRY_STATISTICS     registryStatistics
);
```

## Parameters
* `registryManagerHandle` The handle created by a call to the create function. 

* `registryStatistics` Input parameter, if it is not NULL will contain the requested registry info.

## Return Value
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

