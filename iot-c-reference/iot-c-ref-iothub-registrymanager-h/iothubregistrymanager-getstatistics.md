# IoTHubRegistryManager_GetStatistics()

\#include "[azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h](../iot-c-ref-iothub-registrymanager-h.md)"  

## Syntax

```C
IOTHUB_REGISTRYMANAGER_RESULT IoTHubRegistryManager_GetStatistics(
  IOTHUB_REGISTRYMANAGER_HANDLE  registryManagerHandle,
  IOTHUB_REGISTRY_STATISTICS     registryStatistics
);
```

Gets the registry statistic info.

## Parameters
* `registryManagerHandle`The handle created by a call to the create function. 

* `registryStatistics`Input parameter, if it is not NULL will contain the requested registry info.

## Returns
IOTHUB_REGISTRYMANAGER_RESULT_OK upon success or an error code upon failure.

