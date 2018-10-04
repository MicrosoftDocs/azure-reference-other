# IoTHubClient_UploadMultipleBlocksToBlobAsync()

\#include ["azure-iot-sdk-c/iothub_client/inc/iothub_client.h"](../iot-c-ref-iothub-client-h.md)  

[`IOTHUB_CLIENT_RESULT`](#iothub__client__core__common_8h_1ae8e8840cc715c54bc60465f3f110d40f) `[`IoTHubClient_UploadMultipleBlocksToBlobAsync`](#iothub__client_8h_1aa8e45112bb591d443cd8f71c98bd445e)(`[`IOTHUB_CLIENT_HANDLE`](#iothub__client_8h_1a228b1409767f2560aa0724caad86fd6d) iotHubClientHandle,const char * destinationFileName,`[`IOTHUB_CLIENT_FILE_UPLOAD_GET_DATA_CALLBACK`](#iothub__client__core__common_8h_1a188fa4251310dad00defabb8f77a292f) getDataCallback,void * context)`

Uploads a file to a Blob storage in chunks, fed through the callback function provided by the user.

DEPRECATED: Use IoTHubClient_UploadMultipleBlocksToBlobAsyncEx instead ** This function allows users to upload large files in chunks, not requiring the whole file content to be passed in memory. 

#### Parameters
* `iotHubClientHandle` The handle created by a call to the IoTHubClient_Create function. 

* `destinationFileName` The name of the file to be created in Azure Blob Storage. 

* `getDataCallback` A callback to be invoked to acquire the file chunks to be uploaded, as well as to indicate the status of the upload of the previous block. 

* `context` Any data provided by the user to serve as context on getDataCallback. 

#### Returns
An IOTHUB_CLIENT_RESULT value indicating the success or failure of the API call. DEPRECATED: Use IoTHubClient_UploadMultipleBlocksToBlobAsyncEx instead **

