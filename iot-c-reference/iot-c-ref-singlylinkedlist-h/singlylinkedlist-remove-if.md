# singlylinkedlist_remove_if()

\#include ["azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/singlylinkedlist.h"](../iot-c-ref-singlylinkedlist-h.md)  

## Syntax

```C
int singlylinkedlist_remove_if(
  SINGLYLINKEDLIST_HANDLE  list,
  LIST_CONDITION_FUNCTION  condition_function,
  const void *             match_context
);

```

