# deviceCapabilities_destroy()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_device_capabilities.h"](../iot-c-ref-provisioning-sc-device-capabilities-h.md)  

**void [deviceCapabilities_destroy](#provisioning__sc__device__capabilities_8h_1ae01cf74fe5498757d4da936901b6ac46)([DEVICE_CAPABILITIES_HANDLE](#provisioning__sc__device__capabilities_8h_1af33545b05ae4501337bcfeaecce34ae4) capabilities)**

Destroys a Device Capabilities handle, freeing all associated memory. Please note that if the Device Capabilities are attached to an Enrollment, this will remove it.

#### Parameters
* `capabilities` The handle of the Device Capabilities to be destroyed

