# IoTHubClient_LL_UploadMultipleBlocksToBlob()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client_ll.h"](../iot-c-ref-iothub-client-ll-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_LL_UploadMultipleBlocksToBlob](#iothub__client__ll_8h_1a1720e09a7d7bc17bcdfaf4612d51b061)([IOTHUB_CLIENT_LL_HANDLE](#iothub__client__ll_8h_1abdbc7b1e6f374be8f2339d8c93f87742) iotHubClientHandle,const char * destinationFileName,[IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK](#iothub__client__core__common_8h_1a188fa4251310dad00defabb8f77a292f) getDataCallback,void * context)**

This API uploads to Azure Storage the content provided block by block by `getDataCallback` under the blob name devicename/.

DEPRECATED: Use IoTHubClient_LL_UploadMultipleBlocksToBlobAsyncEx instead ** 
#### Parameters
* `iotHubClientHandle` The handle created by a call to the create function. 

* `destinationFileName` name of the file. 

* `getDataCallback` A callback to be invoked to acquire the file chunks to be uploaded, as well as to indicate the status of the upload of the previous block. 

* `context` Any data provided by the user to serve as context on getDataCallback.

#### Returns
IOTHUB_CLIENT_OK upon success or an error code upon failure. DEPRECATED: Use IoTHubClient_LL_UploadMultipleBlocksToBlobAsyncEx instead **

