# IoTHubDeviceClient_LL_UploadToBlob()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_device_client_ll.h"](../iot-c-ref-iothub-device-client-ll-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubDeviceClient_LL_UploadToBlob](#iothub__device__client__ll_8h_1a1b8e1336348c641fc40750a5ca256c6d)([IOTHUB_DEVICE_CLIENT_LL_HANDLE](#iothub__device__client__ll_8h_1ab3ed1ccac784de53579181b349fd6616) iotHubClientHandle,const char * destinationFileName,const unsigned char * source,size_t size)**

This API uploads to Azure Storage the content pointed to by `source` having the size `size` under the blob name devicename/.

#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `destinationFileName` name of the file. 

* `source` pointer to the source for file content (can be NULL) 

* `size` the size of the source in memory (if `source` is NULL then size needs to be 0).

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure.

