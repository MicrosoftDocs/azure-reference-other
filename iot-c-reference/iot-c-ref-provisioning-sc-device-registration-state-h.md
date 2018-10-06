# provisioning_sc_device_registration_state.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  
\#include "azure_c_shared_utility/macro_utils.h"  
\#include "parson.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[REGISTRATION_STATUSStrings](./iot-c-ref-provisioning-sc-device-registration-state-h/registration-statusstrings.md)            | 
[REGISTRATION_STATUS_FromString](./iot-c-ref-provisioning-sc-device-registration-state-h/registration-status-fromstring.md)            | 
[deviceRegistrationState_getRegistrationId](./iot-c-ref-provisioning-sc-device-registration-state-h/deviceregistrationstate-getregistrationid.md)            | 
[deviceRegistrationState_getCreatedDateTime](./iot-c-ref-provisioning-sc-device-registration-state-h/deviceregistrationstate-getcreateddatetime.md)            | 
[deviceRegistrationState_getDeviceId](./iot-c-ref-provisioning-sc-device-registration-state-h/deviceregistrationstate-getdeviceid.md)            | 
[deviceRegistrationState_getRegistrationStatus](./iot-c-ref-provisioning-sc-device-registration-state-h/deviceregistrationstate-getregistrationstatus.md)            | 
[deviceRegistrationState_getUpdatedDateTime](./iot-c-ref-provisioning-sc-device-registration-state-h/deviceregistrationstate-getupdateddatetime.md)            | 
[deviceRegistrationState_getErrorCode](./iot-c-ref-provisioning-sc-device-registration-state-h/deviceregistrationstate-geterrorcode.md)            | 
[deviceRegistrationState_getErrorMessage](./iot-c-ref-provisioning-sc-device-registration-state-h/deviceregistrationstate-geterrormessage.md)            | 
[deviceRegistrationState_getEtag](./iot-c-ref-provisioning-sc-device-registration-state-h/deviceregistrationstate-getetag.md)            | 
[deviceRegistrationState_destroy](./iot-c-ref-provisioning-sc-device-registration-state-h/deviceregistrationstate-destroy.md)            | 

## Macro definitions

#### REGISTRATION_STATUS_VALUES

```C
#define REGISTRATION_STATUS_VALUES \
 REGISTRATION_STATUS_ERROR, \
 REGISTRATION_STATUS_UNASSIGNED, \
 REGISTRATION_STATUS_ASSIGNING, \
 REGISTRATION_STATUS_ASSIGNED, \
 REGISTRATION_STATUS_FAILED, \
 REGISTRATION_STATUS_DISABLED 

```

## Enumeration types

#### REGISTRATION_STATUS

```C
enum REGISTRATION_STATUS {
  REGISTRATION_STATUS_ERROR,
  REGISTRATION_STATUS_UNASSIGNED,
  REGISTRATION_STATUS_ASSIGNING,
  REGISTRATION_STATUS_ASSIGNED,
  REGISTRATION_STATUS_FAILED,
  REGISTRATION_STATUS_DISABLED
}

```
Constant                    | Description                                
----------------------------|----------------
 REGISTRATION_STATUS_ERROR            | 
 REGISTRATION_STATUS_UNASSIGNED            | 
 REGISTRATION_STATUS_ASSIGNING            | 
 REGISTRATION_STATUS_ASSIGNED            | 
 REGISTRATION_STATUS_FAILED            | 
 REGISTRATION_STATUS_DISABLED            | 

