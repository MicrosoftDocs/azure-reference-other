# enrollmentGroup_deserializeFromJson()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h"](../iot-c-ref-provisioning-sc-models-serializer-h.md)  

[`ENROLLMENT_GROUP_HANDLE`](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) `[`enrollmentGroup_deserializeFromJson`](#provisioning__sc__models__serializer_8h_1ae385a17e35fd22274b47441eaa5dd0dd)(const char * json_string)`

Deserializes a JSON String representation of an Enrollment Group.

#### Parameters
* `json_string` A JSON String representing an Enrollment Group.

#### Returns
A non-NULL handle representing an Enrollment Group, and NULL on failure.

