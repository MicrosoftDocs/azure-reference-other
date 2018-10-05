# initialTwin_destroy()

Destroys an Initial Twin handle, freeing all associated memory. Please note that this will also cause any Enrollment that the Initial Twin has been attached to to have unexpected behvaiours. Do not use this function unless the Initial Twin is unattached.

## Syntax

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_twin.h](../iot-c-ref-provisioning-sc-twin-h.md)"  
```C
void initialTwin_destroy(
  INITIAL_TWIN_HANDLE  twin
);
```

## Parameters
* `twin` The handle of the Initial Twin to be destroyed

