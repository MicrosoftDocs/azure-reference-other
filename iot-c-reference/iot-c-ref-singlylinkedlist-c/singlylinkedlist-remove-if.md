# singlylinkedlist_remove_if()

## Syntax

\#include "[azure-iot-sdk-c/c-utility/src/singlylinkedlist.c](../iot-c-ref-singlylinkedlist.c.md)"  
```C
int singlylinkedlist_remove_if(
  SINGLYLINKEDLIST_HANDLE  list,
  LIST_CONDITION_FUNCTION  condition_function,
  const void *             match_context
);
```

