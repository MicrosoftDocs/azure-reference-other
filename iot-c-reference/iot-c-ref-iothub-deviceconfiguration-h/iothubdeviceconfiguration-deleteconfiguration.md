# IoTHubDeviceConfiguration_DeleteConfiguration()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h"](../iot-c-ref-iothub-deviceconfiguration-h.md)  

**[IOTHUB_DEVICE_CONFIGURATION_RESULT](#iothub__deviceconfiguration_8h_1ac7d4e5e1c224c46fc993541e145b59d6) [IoTHubDeviceConfiguration_DeleteConfiguration](#iothub__deviceconfiguration_8h_1aff7e7d0bcdb39e99c434c4adbc0046be)([IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE](#iothub__deviceconfiguration_8h_1a6b6d0ee5e70f65ee692e420e50ef805c) serviceClientDeviceConfigurationHandle,const char * configurationId)**

Deletes the given Configuration from IoT Hub.

#### Parameters
* `serviceClientDeviceConfigurationHandle` The handle created by a call to the create function. 

* `configurationId` The configuration name (id) to delete Configuration info for.

#### Returns
IOTHUB_DEVICE_CONFIGURATION_RESULT upon success or an error code upon failure.

