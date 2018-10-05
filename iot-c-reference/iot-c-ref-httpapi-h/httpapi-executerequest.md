# HTTPAPI_ExecuteRequest()

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/httpapi.h](../iot-c-ref-httpapi-h.md)"  

## Syntax

```C
HTTPAPI_RESULT HTTPAPI_ExecuteRequest(
  HTTP_HANDLE            handle,

  HTTPAPI_REQUEST_TYPE   requestType,

  const char *           relativePath,

  HTTP_HEADERS_HANDLE    httpHeadersHandle,

  const unsigned char *  content,

  size_t                 contentLength,

  unsigned int *         statusCode,

  HTTP_HEADERS_HANDLE    responseHeadersHandle,

  BUFFER_HANDLE          responseContent
);
```

Sends the HTTP request to the host and handles the response for the HTTP call.

## Parameters
* **:handle** The handle to the HTTP connection created via [HTTPAPI_CreateConnection](#httpapi_8h_1a96629fdbe1b52a5357da60bb1248b174). 

* **:requestType** Specifies which HTTP method is used (GET, POST, DELETE, PUT, PATCH). 

* **:relativePath** Specifies the relative path of the URL excluding the host name. 

* **:httpHeadersHandle** Specifies a set of HTTP headers (name-value pairs) to be added to the HTTP request. The `httpHeadersHandle` handle can be created and setup with the proper name-value pairs by using the HTTPHeaders APIs available in `HTTPHeaders.h`. 

* **:content** Specifies a pointer to the request body. This value is optional and can be `NULL`. 

* **:contentLength** Specifies the request body size (this is typically added into the HTTP headers as the Content-Length header). This value is optional and can be 0. 

* **:statusCode** This is an out parameter, where [HTTPAPI_ExecuteRequest](#httpapi_8h_1afa60b8d96e73b2fe592b591208ef66b1) returns the status code from the HTTP response (200, 201, 400, 401, etc.) 

* **:responseHeadersHandle** This is an HTTP headers handle to which [HTTPAPI_ExecuteRequest](#httpapi_8h_1afa60b8d96e73b2fe592b591208ef66b1) must add all the HTTP response headers so that the caller of [HTTPAPI_ExecuteRequest](#httpapi_8h_1afa60b8d96e73b2fe592b591208ef66b1) can inspect them. You can manipulate `responseHeadersHandle` by using the HTTPHeaders APIs available in `HTTPHeaders.h`

* **:responseContent** This is a buffer that must be filled by [HTTPAPI_ExecuteRequest](#httpapi_8h_1afa60b8d96e73b2fe592b591208ef66b1) with the contents of the HTTP response body. The buffer size must be increased by the [HTTPAPI_ExecuteRequest](#httpapi_8h_1afa60b8d96e73b2fe592b591208ef66b1) implementation in order to fit the response body. [HTTPAPI_ExecuteRequest](#httpapi_8h_1afa60b8d96e73b2fe592b591208ef66b1) must also handle chunked transfer encoding for HTTP responses. To manipulate the `responseContent` buffer, use the APIs available in `[Strings.h](#strings_8h)`.

## Returns
`HTTPAPI_OK` if the API call is successful or an error code in case it fails.

