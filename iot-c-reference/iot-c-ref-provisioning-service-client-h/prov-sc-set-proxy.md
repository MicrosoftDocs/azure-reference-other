# prov_sc_set_proxy()

\#include ["azure-iot-sdk-c/provisioning_service_client/inc/prov_service_client/provisioning_service_client.h"](../iot-c-ref-provisioning-service-client-h.md)  

**int [prov_sc_set_proxy](#provisioning__service__client_8h_1aaa19266190d48360bcd3185013f22496)([PROVISIONING_SERVICE_CLIENT_HANDLE](#provisioning__service__client_8h_1af84a07c4286fd5d90fc2871d08cd0d0d) prov_client,[HTTP_PROXY_OPTIONS](#struct_h_t_t_p___p_r_o_x_y___o_p_t_i_o_n_s) * proxy_options)**

Set the proxy options for HTTP communication with the Provisioning Service.

#### Parameters
* `prov_client` The handle used for connecting to the Provisioning Service. 

* `proxy_options` A struct containing the desired proxy settings

#### Returns
0 upon success, a non-zero number upon failure.

