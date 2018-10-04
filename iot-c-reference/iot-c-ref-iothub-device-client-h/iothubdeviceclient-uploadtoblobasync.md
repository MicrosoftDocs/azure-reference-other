# IoTHubDeviceClient_UploadToBlobAsync()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client.h"](../iot-c-ref-iothub-device-client-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_UploadToBlobAsync](#iothub__device__client_8h_1a3ec9c3d33886fd7814dab05e074512cd)([IOTHUB_DEVICE_CLIENT_HANDLE](#iothub__device__client_8h_1ac0a6393bbcbec2e1b580e8c4c127f4c1) iotHubClientHandle,const char * destinationFileName,const unsigned char * source,size_t size,[IOTHUB_CLIENT_FILE_UPLOAD_CALLBACK](#iothub__client__core__common_8h_1a039d574a949c85ba9c183c88d4ce03bf) iotHubClientFileUploadCallback,void * context)**

IoTHubDeviceClient_UploadToBlobAsync uploads data from memory to a file in Azure Blob Storage.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the IoTHubDeviceClient_Create function. 

* `destinationFileName` The name of the file to be created in Azure Blob Storage. 

* `source` The source of data. 

* `size` The size of data. 

* `iotHubClientFileUploadCallback` A callback to be invoked when the file upload operation has finished. 

* `context` A user-provided context to be passed to the file upload callback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

