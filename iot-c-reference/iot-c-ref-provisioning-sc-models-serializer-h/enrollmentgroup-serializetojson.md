# enrollmentGroup_serializeToJson()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h"](../iot-c-ref-provisioning-sc-models-serializer-h.md)  

char * `[`enrollmentGroup_serializeToJson`](#provisioning__sc__models__serializer_8h_1a34aa155f69d90a364cf3a968448416cd)(const `[`ENROLLMENT_GROUP_HANDLE`](#provisioning__sc__enrollment_8h_1a708e4d11b8ea003be46d259a70c637bb) enrollment)`

Serializes an Enrollment Group into a JSON String.

#### Parameters
* `enrollment` A handle for the Enrollment Group to be serialized.

#### Returns
A non-NULL string containing the serialized JSON String, and NULL on failure.

