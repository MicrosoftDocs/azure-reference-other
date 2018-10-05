# deviceCapabilities_destroy()

Destroys a Device Capabilities handle, freeing all associated memory. Please note that if the Device Capabilities are attached to an Enrollment, this will remove it.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_device_capabilities.h](../iot-c-ref-provisioning-sc-device-capabilities-h.md)"  
```C
void deviceCapabilities_destroy(
  DEVICE_CAPABILITIES_HANDLE  capabilities
);
```

## Parameters
* `capabilities` The handle of the Device Capabilities to be destroyed

