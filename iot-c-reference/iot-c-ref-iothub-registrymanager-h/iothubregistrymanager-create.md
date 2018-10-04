# IoTHubRegistryManager_Create()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_registrymanager.h"](../iot-c-ref-iothub-registrymanager-h.md)  

**[IOTHUB_REGISTRYMANAGER_HANDLE](#iothub__registrymanager_8h_1ac3e429abedd42575f91088247225387f) [IoTHubRegistryManager_Create](#iothub__registrymanager_8h_1aefe8d92083c2d44591de4350b5bcb03e)([IOTHUB_SERVICE_CLIENT_AUTH_HANDLE](#iothub__service__client__auth_8h_1a47d2f6357931c33108eb9fba95d8730b) serviceClientHandle)**

Creates a IoT Hub Registry Manager handle for use it in consequent APIs.

#### Parameters
* `serviceClientHandle` Service client handle.

#### Returns
A non-NULL `IOTHUB_REGISTRYMANAGER_HANDLE` value that is used when invoking other functions for IoT Hub REgistry Manager and `NULL` on failure.

