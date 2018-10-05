# deviceCapabilities_create()

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_device_capabilities.h](../iot-c-ref-provisioning-sc-device-capabilities-h.md)"  

## Syntax

```C
DEVICE_CAPABILITIES_HANDLE deviceCapabilities_create(void);
```

Creates a Device Capabilities handle that can be used in consequent APIs, with all fields initialized to "false".

## Returns
A non-NULL handle representing Device Capabilities for use with the Provisioning Service, and NULL on failure.

