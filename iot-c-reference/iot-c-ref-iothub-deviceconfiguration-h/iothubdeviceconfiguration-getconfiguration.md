# IoTHubDeviceConfiguration_GetConfiguration()

\#include ["azure-iot-sdk-c/iothub_service_client/inc/iothub_deviceconfiguration.h"](../iot-c-ref-iothub-deviceconfiguration-h.md)  

## Syntax

```C
IOTHUB_DEVICE_CONFIGURATION_RESULT IoTHubDeviceConfiguration_GetConfiguration(
  IOTHUB_SERVICE_CLIENT_DEVICE_CONFIGURATION_HANDLE  	serviceClientDeviceConfigurationHandle,
  const char *                                       	configurationId,
  IOTHUB_DEVICE_CONFIGURATION                        	configuration
);

```

Retrieves the Configuration info for specified configurationId from IoT Hub.

#### Parameters
* `serviceClientDeviceConfigurationHandle` The handle created by a call to the create function. 

* `configurationId` The configuration name (id) to retrieve Configuration info for. 

* `configuration` Output parameter, if it is not NULL will contain the requested configuration info structure

#### Returns
IOTHUB_DEVICE_CONFIGURATION_RESULT upon success or an error code upon failure.

