# singlylinkedlist_foreach()

## Syntax

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/singlylinkedlist.h](../iot-c-ref-singlylinkedlist-h.md)"  
```C
int singlylinkedlist_foreach(
  SINGLYLINKEDLIST_HANDLE  list,
  LIST_ACTION_FUNCTION     action_function,
  const void *             action_context
);
```

