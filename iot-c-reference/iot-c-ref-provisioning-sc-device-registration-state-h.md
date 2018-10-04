# Header file provisioning_sc_device_registration_state.h 

Stub comment for brief. Please update this comment.

## Includes

\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
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

## Defines

Define Name                    | Value                                
--------------------------------|---------------------------------------------
REGISTRATION_STATUS_VALUES            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
DEVICE_REGISTRATION_STATE_HANDLE            | 

## Function documentation

#### REGISTRATION_STATUSStrings 
const char * `[`REGISTRATION_STATUSStrings`](#provisioning__sc__device__registration__state_8h_1a5b9b942e2a55861dda96b4a6ca0a53db)(`[`REGISTRATION_STATUS`](#provisioning__sc__device__registration__state_8h_1a9f27132cc8d0c5116bf55aecce9dabec) value)`

#### REGISTRATION_STATUS_FromString 
int `[`REGISTRATION_STATUS_FromString`](#provisioning__sc__device__registration__state_8h_1adea122059d7ee30471eb2aaac6388e8f)(const char * enumAsString,`[`REGISTRATION_STATUS`](#provisioning__sc__device__registration__state_8h_1a9f27132cc8d0c5116bf55aecce9dabec) * destination)`

#### deviceRegistrationState_getRegistrationId 
const char * `[`deviceRegistrationState_getRegistrationId`](#provisioning__sc__device__registration__state_8h_1a58763b3acf78a5524dc6bab085aab82a)(`[`DEVICE_REGISTRATION_STATE_HANDLE`](#provisioning__sc__device__registration__state_8h_1a52841b38d699231f85846525109d2804) drs)`

#### deviceRegistrationState_getCreatedDateTime 
const char * `[`deviceRegistrationState_getCreatedDateTime`](#provisioning__sc__device__registration__state_8h_1a169a2d1449e6a9804861f027ca55d1ee)(`[`DEVICE_REGISTRATION_STATE_HANDLE`](#provisioning__sc__device__registration__state_8h_1a52841b38d699231f85846525109d2804) drs)`

#### deviceRegistrationState_getDeviceId 
const char * `[`deviceRegistrationState_getDeviceId`](#provisioning__sc__device__registration__state_8h_1a0403f3823d50ad1a8100c618b9ce7c4a)(`[`DEVICE_REGISTRATION_STATE_HANDLE`](#provisioning__sc__device__registration__state_8h_1a52841b38d699231f85846525109d2804) drs)`

#### deviceRegistrationState_getRegistrationStatus 
[`REGISTRATION_STATUS`](#provisioning__sc__device__registration__state_8h_1a9f27132cc8d0c5116bf55aecce9dabec) `[`deviceRegistrationState_getRegistrationStatus`](#provisioning__sc__device__registration__state_8h_1ab2f1ddc166b57710dca1cfd437c119e3)(`[`DEVICE_REGISTRATION_STATE_HANDLE`](#provisioning__sc__device__registration__state_8h_1a52841b38d699231f85846525109d2804) drs)`

#### deviceRegistrationState_getUpdatedDateTime 
const char * `[`deviceRegistrationState_getUpdatedDateTime`](#provisioning__sc__device__registration__state_8h_1afbfa78554cd5d0d73a4165d37aed8f27)(`[`DEVICE_REGISTRATION_STATE_HANDLE`](#provisioning__sc__device__registration__state_8h_1a52841b38d699231f85846525109d2804) drs)`

#### deviceRegistrationState_getErrorCode 
int `[`deviceRegistrationState_getErrorCode`](#provisioning__sc__device__registration__state_8h_1ad2189583484f737945abb71f2a454a1d)(`[`DEVICE_REGISTRATION_STATE_HANDLE`](#provisioning__sc__device__registration__state_8h_1a52841b38d699231f85846525109d2804) drs)`

#### deviceRegistrationState_getErrorMessage 
const char * `[`deviceRegistrationState_getErrorMessage`](#provisioning__sc__device__registration__state_8h_1ab68533f53f801721d1dab58cc0cb2b4e)(`[`DEVICE_REGISTRATION_STATE_HANDLE`](#provisioning__sc__device__registration__state_8h_1a52841b38d699231f85846525109d2804) drs)`

#### deviceRegistrationState_getEtag 
const char * `[`deviceRegistrationState_getEtag`](#provisioning__sc__device__registration__state_8h_1a52ebd543bb4bc80a92d7672f3767e192)(`[`DEVICE_REGISTRATION_STATE_HANDLE`](#provisioning__sc__device__registration__state_8h_1a52841b38d699231f85846525109d2804) drs)`

#### deviceRegistrationState_destroy 
void `[`deviceRegistrationState_destroy`](#provisioning__sc__device__registration__state_8h_1aa4b69c4a0b654ec04da3270584e7b390)(`[`DEVICE_REGISTRATION_STATE_HANDLE`](#provisioning__sc__device__registration__state_8h_1a52841b38d699231f85846525109d2804) device_reg_state)`

