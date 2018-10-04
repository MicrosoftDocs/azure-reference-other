# initialTwin_create()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_twin.h"](../iot-c-ref-provisioning-sc-twin-h.md)  

[`INITIAL_TWIN_HANDLE`](#provisioning__sc__twin_8h_1a8230047b4f4613e6691e5a741e65797f) `[`initialTwin_create`](#provisioning__sc__twin_8h_1acd67fdca9ae906efdb7c10c64418ee23)(const char * tags,const char * desired_properties)`

Creates an Initial Twin handle for use in consequent APIs.

#### Parameters
* `tags` The json string for the tags of the initial Twin State 

* `desired_properties` The json string for the desired properties of the initial Twin State

#### Returns
A non-NULL handle representing an Initial Twin for use with Provisioning Service, and NULL on failure.

