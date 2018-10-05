# singlylinkedlist.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "stdbool.h"  
\#include "[azure_c_shared_utility/umock_c_prod.h](iot-c-ref-umock-c-prod-h.md)"  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[singlylinkedlist_create](./iot-c-ref-singlylinkedlist-h/singlylinkedlist-create.md)            | 
[singlylinkedlist_destroy](./iot-c-ref-singlylinkedlist-h/singlylinkedlist-destroy.md)            | 
[singlylinkedlist_add](./iot-c-ref-singlylinkedlist-h/singlylinkedlist-add.md)            | 
[singlylinkedlist_remove](./iot-c-ref-singlylinkedlist-h/singlylinkedlist-remove.md)            | 
[singlylinkedlist_get_head_item](./iot-c-ref-singlylinkedlist-h/singlylinkedlist-get-head-item.md)            | 
[singlylinkedlist_get_next_item](./iot-c-ref-singlylinkedlist-h/singlylinkedlist-get-next-item.md)            | 
[singlylinkedlist_find](./iot-c-ref-singlylinkedlist-h/singlylinkedlist-find.md)            | 
[singlylinkedlist_item_get_value](./iot-c-ref-singlylinkedlist-h/singlylinkedlist-item-get-value.md)            | 
[singlylinkedlist_remove_if](./iot-c-ref-singlylinkedlist-h/singlylinkedlist-remove-if.md)            | 
[singlylinkedlist_foreach](./iot-c-ref-singlylinkedlist-h/singlylinkedlist-foreach.md)            | 

## Typedefs

#### SINGLYLINKEDLIST_HANDLE

```C
typedef struct SINGLYLINKEDLIST_INSTANCE_TAG * SINGLYLINKEDLIST_HANDLE;

```

#### LIST_ITEM_HANDLE

```C
typedef struct LIST_ITEM_INSTANCE_TAG * LIST_ITEM_HANDLE;

```

#### LIST_MATCH_FUNCTION

```C
typedef bool(* LIST_MATCH_FUNCTION;

```

Function passed to singlylinkedlist_find, which returns whichever first list item that matches it.

#### LIST_CONDITION_FUNCTION

```C
typedef bool(* LIST_CONDITION_FUNCTION;

```

Function passed to singlylinkedlist_remove_if, which is used to define if an item of the list should be removed or not.

#### LIST_ACTION_FUNCTION

```C
typedef void(* LIST_ACTION_FUNCTION;

```

Function passed to singlylinkedlist_foreach, which is called for the value of each node of the list.

