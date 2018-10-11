# shared_util_options.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "azure_c_shared_utility/const_defines.h"  

## Detailed Description

Stub comment for details. Please update this comment.

## Structures

#### HTTP_PROXY_OPTIONS

```C
struct HTTP_PROXY_OPTIONS {
  const char *  host_address,
  int           port,
  const char *  username,
  const char *  password
};
```
Member name                 | Description                                
----------------------------|----------------
 host_address            | 
 port            | 
 username            | 
 password            | 

## Constants and Variables

#### OPTION_HTTP_PROXY
```C
const char* const OPTION_HTTP_PROXY = "proxy_data";
```

#### OPTION_HTTP_TIMEOUT
```C
const char* const OPTION_HTTP_TIMEOUT = "timeout";
```

#### OPTION_TRUSTED_CERT
```C
const char* const OPTION_TRUSTED_CERT = "TrustedCerts";
```

#### OPTION_OPENSSL_CIPHER_SUITE
```C
const char* const OPTION_OPENSSL_CIPHER_SUITE = "CipherSuite";
```

#### SU_OPTION_X509_CERT
```C
const char* const SU_OPTION_X509_CERT = "x509certificate";
```

#### SU_OPTION_X509_PRIVATE_KEY
```C
const char* const SU_OPTION_X509_PRIVATE_KEY = "x509privatekey";
```

#### OPTION_X509_ECC_CERT
```C
const char* const OPTION_X509_ECC_CERT = "x509EccCertificate";
```

#### OPTION_X509_ECC_KEY
```C
const char* const OPTION_X509_ECC_KEY = "x509EccAliasKey";
```

#### OPTION_CURL_LOW_SPEED_LIMIT
```C
const char* const OPTION_CURL_LOW_SPEED_LIMIT = "CURLOPT_LOW_SPEED_LIMIT";
```

#### OPTION_CURL_LOW_SPEED_TIME
```C
const char* const OPTION_CURL_LOW_SPEED_TIME = "CURLOPT_LOW_SPEED_TIME";
```

#### OPTION_CURL_FRESH_CONNECT
```C
const char* const OPTION_CURL_FRESH_CONNECT = "CURLOPT_FRESH_CONNECT";
```

#### OPTION_CURL_FORBID_REUSE
```C
const char* const OPTION_CURL_FORBID_REUSE = "CURLOPT_FORBID_REUSE";
```

#### OPTION_CURL_VERBOSE
```C
const char* const OPTION_CURL_VERBOSE = "CURLOPT_VERBOSE";
```

#### OPTION_NET_INT_MAC_ADDRESS
```C
const char* const OPTION_NET_INT_MAC_ADDRESS = "net_interface_mac_address";
```

#### OPTION_TLS_VERSION
```C
const char* const OPTION_TLS_VERSION = "tls_version";
```

#### OPTION_ADDRESS_TYPE
```C
const char* const OPTION_ADDRESS_TYPE = "ADDRESS_TYPE";
```

#### OPTION_ADDRESS_TYPE_DOMAIN_SOCKET
```C
const char* const OPTION_ADDRESS_TYPE_DOMAIN_SOCKET = "DOMAIN_SOCKET";
```

#### OPTION_ADDRESS_TYPE_IP_SOCKET
```C
const char* const OPTION_ADDRESS_TYPE_IP_SOCKET = "IP_SOCKET";
```

