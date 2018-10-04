# initialTwin_destroy()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_twin.h"](../iot-c-ref-provisioning-sc-twin-h.md)  

**void [initialTwin_destroy](#provisioning__sc__twin_8h_1a3819b321db3a376deb5cc44d99131bec)([INITIAL_TWIN_HANDLE](#provisioning__sc__twin_8h_1a8230047b4f4613e6691e5a741e65797f) twin)**

Destroys an Initial Twin handle, freeing all associated memory. Please note that this will also cause any Enrollment that the Initial Twin has been attached to to have unexpected behvaiours. Do not use this function unless the Initial Twin is unattached.

#### Parameters
* `twin` The handle of the Initial Twin to be destroyed

