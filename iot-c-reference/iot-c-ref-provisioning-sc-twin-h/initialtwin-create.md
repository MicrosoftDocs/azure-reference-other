# initialTwin_create()

\#include "[azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_twin.h](../iot-c-ref-provisioning-sc-twin-h.md)"  

## Syntax

```C
INITIAL_TWIN_HANDLE initialTwin_create(
  const char *  tags,
  const char *  desired_properties);
```

Creates an Initial Twin handle for use in consequent APIs.

## Parameters
* `tags`The json string for the tags of the initial Twin State 

* `desired_properties`The json string for the desired properties of the initial Twin State

## Returns
A non-NULL handle representing an Initial Twin for use with Provisioning Service, and NULL on failure.

