# IoTHubClient_UploadMultipleBlocksToBlobAsyncEx()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client.h"](../iot-c-ref-iothub-client-h.md)  

**[IOTHUB_CLIENT_RESULT](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) [IoTHubClient_UploadMultipleBlocksToBlobAsyncEx](#iothub__client_8h_1a2e3c65d775ffa45a05b7e7052b3bc088)([IOTHUB_CLIENT_HANDLE](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,const char * destinationFileName,[IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK_EX](#iothub__client__core__common_8h_1a0d9944dec4c4dd2bdd75cebb466dcf6c) getDataCallbackEx,void * context)**

Uploads a file to a Blob storage in chunks, fed through the callback function provided by the user.

This function allows users to upload large files in chunks, not requiring the whole file content to be passed in memory. 

#### Parameters
* `iotHubClientHandle` The handle created by a call to the IoTHubClient_Create function. 

* `destinationFileName` The name of the file to be created in Azure Blob Storage. 

* `getDataCallbackEx` A callback to be invoked to acquire the file chunks to be uploaded, as well as to indicate the status of the upload of the previous block. 

* `context` Any data provided by the user to serve as context on getDataCallback. 

#### Returns
An IOTHUB_CLIENT_RESULT value indicating the success or failure of the API call.

