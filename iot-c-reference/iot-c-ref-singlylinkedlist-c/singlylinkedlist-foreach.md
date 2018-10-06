# singlylinkedlist_foreach()

## Syntax

\#include "[azure-iot-sdk-c/c-utility/src/singlylinkedlist.c](../iot-c-ref-singlylinkedlist.c.md)"  
```C
int singlylinkedlist_foreach(
  SINGLYLINKEDLIST_HANDLE  list,
  LIST_ACTION_FUNCTION     action_function,
  const void *             action_context
);
```

