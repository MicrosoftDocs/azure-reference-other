# individualEnrollment_serializeToJson()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_sc_models_serializer.h"](../iot-c-ref-provisioning-sc-models-serializer-h.md)  

**char * [individualEnrollment_serializeToJson](#provisioning__sc__models__serializer_8h_1a9d9736511910a28158e9604bf867aee8)(const [INDIVIDUAL_ENROLLMENT_HANDLE](#provisioning__sc__enrollment_8h_1a5348427a740bc7d9395db2e190f1bc0f) enrollment)**

Serializes an Individual Enrollment into a JSON String.

#### Parameters
* `enrollment` A handle for the Individual Enrollment to be serialized.

#### Returns
A non-NULL string containing the serialized JSON String, and NULL on failure.

