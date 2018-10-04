# IoTHubDeviceConfiguration_GetConfigurations()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h"](../iot-c-ref-iothub-deviceconfiguration-h.md)  

**[IOTHUB_DEVICE_CONFIGURATION_RESULT](#iothub__deviceconfiguration_8h_1ac7d4e5e1c224c46fc993541e145b59d6) [IoTHubDeviceConfiguration_GetConfigurations](#iothub__deviceconfiguration_8h_1a76b5c792dd547475f8850a21cc0c95c1)([IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE](#iothub__deviceconfiguration_8h_1a6b6d0ee5e70f65ee692e420e50ef805c) serviceClientDeviceConfigurationHandle,size_t maxConfigurationsCount,[SINGLYLINKEDLIST_HANDLE](#singlylinkedlist_8h_1a355ba061e4132f7817d6d1963d33382a) configurationsList)**

Retrieves the Configuration info for multiple configurations from IoT Hub.

#### Parameters
* `serviceClientDeviceConfigurationHandle` The handle created by a call to the create function. 

* `maxConfigurationsCount` Maximum number of configurations requested 

* `configurations` Output parameter, if it is not NULL will contain the requested configurations

#### Returns
IOTHUB_DEVICE_CONFIGURATION_RESULT upon success or an error code upon failure.

