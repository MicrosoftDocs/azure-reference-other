# singlylinkedlist.c 

## Includes

\#include <stdlib.h>  
\#include "[azure_c_shared_utility/gballoc.h](iot-c-ref-gballoc-h.md)"  
\#include "[azure_c_shared_utility/singlylinkedlist.h](iot-c-ref-singlylinkedlist-h.md)"  
\#include "azure_c_shared_utility/optimize_size.h"  
\#include "[azure_c_shared_utility/xlogging.h](iot-c-ref-xlogging-h.md)"  

## Detailed Description

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[singlylinkedlist_create](./iot-c-ref-singlylinkedlist-c/singlylinkedlist-create.md)            | 
[singlylinkedlist_destroy](./iot-c-ref-singlylinkedlist-c/singlylinkedlist-destroy.md)            | 
[singlylinkedlist_add](./iot-c-ref-singlylinkedlist-c/singlylinkedlist-add.md)            | 
[singlylinkedlist_remove](./iot-c-ref-singlylinkedlist-c/singlylinkedlist-remove.md)            | 
[singlylinkedlist_get_head_item](./iot-c-ref-singlylinkedlist-c/singlylinkedlist-get-head-item.md)            | 
[singlylinkedlist_get_next_item](./iot-c-ref-singlylinkedlist-c/singlylinkedlist-get-next-item.md)            | 
[singlylinkedlist_item_get_value](./iot-c-ref-singlylinkedlist-c/singlylinkedlist-item-get-value.md)            | 
[singlylinkedlist_find](./iot-c-ref-singlylinkedlist-c/singlylinkedlist-find.md)            | 
[singlylinkedlist_remove_if](./iot-c-ref-singlylinkedlist-c/singlylinkedlist-remove-if.md)            | 
[singlylinkedlist_foreach](./iot-c-ref-singlylinkedlist-c/singlylinkedlist-foreach.md)            | 

## Structures

#### LIST_ITEM_INSTANCE

```C
struct LIST_ITEM_INSTANCE {
  const void *  item,
  void *        next
};
```
Member name                 | Description                                
----------------------------|----------------
 item            | 
 next            | 
#### LIST_INSTANCE

```C
struct LIST_INSTANCE {
  [LIST_ITEM_INSTANCE](#undefined) *  head,
  [LIST_ITEM_INSTANCE](#undefined) *  tail
};
```
Member name                 | Description                                
----------------------------|----------------
 head            | 
 tail            | 

