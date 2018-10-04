# Header file singlylinkedlist.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "stdbool.h"  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  

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

Typedef                        | Value                                
--------------------------------|---------------------------------------------
SINGLYLINKEDLIST_HANDLE            | 
LIST_ITEM_HANDLE            | 
LIST_MATCH_FUNCTION            | Function passed to singlylinkedlist_find, which returns whichever first list item that matches it.
LIST_CONDITION_FUNCTION            | Function passed to singlylinkedlist_remove_if, which is used to define if an item of the list should be removed or not.
LIST_ACTION_FUNCTION            | Function passed to singlylinkedlist_foreach, which is called for the value of each node of the list.

## Function documentation

#### singlylinkedlist_create 
[`SINGLYLINKEDLIST_HANDLE`](#singlylinkedlist_8h_1a355ba061e4132f7817d6d1963d33382a) `[`singlylinkedlist_create`](#singlylinkedlist_8h_1ab0c5ab1106ca4f392541c044fe8a1f13)(void)`

#### singlylinkedlist_destroy 
void `[`singlylinkedlist_destroy`](#singlylinkedlist_8h_1af882d0a8dedb9091e5e77df980e631ff)(`[`SINGLYLINKEDLIST_HANDLE`](#singlylinkedlist_8h_1a355ba061e4132f7817d6d1963d33382a) list)`

#### singlylinkedlist_add 
[`LIST_ITEM_HANDLE`](#singlylinkedlist_8h_1ae362527c1f19954b3aecaa976f6c53ca) `[`singlylinkedlist_add`](#singlylinkedlist_8h_1a42bf74145425439976828ec33f4642e9)(`[`SINGLYLINKEDLIST_HANDLE`](#singlylinkedlist_8h_1a355ba061e4132f7817d6d1963d33382a) list,const void * item)`

#### singlylinkedlist_remove 
int `[`singlylinkedlist_remove`](#singlylinkedlist_8h_1aa6b1f1e802077b4146bf2a00069539aa)(`[`SINGLYLINKEDLIST_HANDLE`](#singlylinkedlist_8h_1a355ba061e4132f7817d6d1963d33382a) list,`[`LIST_ITEM_HANDLE`](#singlylinkedlist_8h_1ae362527c1f19954b3aecaa976f6c53ca) item_handle)`

#### singlylinkedlist_get_head_item 
[`LIST_ITEM_HANDLE`](#singlylinkedlist_8h_1ae362527c1f19954b3aecaa976f6c53ca) `[`singlylinkedlist_get_head_item`](#singlylinkedlist_8h_1a2557a2e240bd38a36a240a8386096507)(`[`SINGLYLINKEDLIST_HANDLE`](#singlylinkedlist_8h_1a355ba061e4132f7817d6d1963d33382a) list)`

#### singlylinkedlist_get_next_item 
[`LIST_ITEM_HANDLE`](#singlylinkedlist_8h_1ae362527c1f19954b3aecaa976f6c53ca) `[`singlylinkedlist_get_next_item`](#singlylinkedlist_8h_1a49c10339cc9944b7a7028c25b557f1ef)(`[`LIST_ITEM_HANDLE`](#singlylinkedlist_8h_1ae362527c1f19954b3aecaa976f6c53ca) item_handle)`

#### singlylinkedlist_find 
[`LIST_ITEM_HANDLE`](#singlylinkedlist_8h_1ae362527c1f19954b3aecaa976f6c53ca) `[`singlylinkedlist_find`](#singlylinkedlist_8h_1aa2298421f28b41698856027ee5b3eca2)(`[`SINGLYLINKEDLIST_HANDLE`](#singlylinkedlist_8h_1a355ba061e4132f7817d6d1963d33382a) list,`[`LIST_MATCH_FUNCTION`](#singlylinkedlist_8h_1ac4ef8d3a98b441078368c9c67367e196) match_function,const void * match_context)`

#### singlylinkedlist_item_get_value 
const void * `[`singlylinkedlist_item_get_value`](#singlylinkedlist_8h_1ae1a394b3f989a78faa77ce2aa11e1c67)(`[`LIST_ITEM_HANDLE`](#singlylinkedlist_8h_1ae362527c1f19954b3aecaa976f6c53ca) item_handle)`

#### singlylinkedlist_remove_if 
int `[`singlylinkedlist_remove_if`](#singlylinkedlist_8h_1aaf7a647fe18bb2b27f88b75f0ba35f72)(`[`SINGLYLINKEDLIST_HANDLE`](#singlylinkedlist_8h_1a355ba061e4132f7817d6d1963d33382a) list,`[`LIST_CONDITION_FUNCTION`](#singlylinkedlist_8h_1a49f50084658ac99a65bbd08a9dd6aa92) condition_function,const void * match_context)`

#### singlylinkedlist_foreach 
int `[`singlylinkedlist_foreach`](#singlylinkedlist_8h_1a808807add589fa522458d5a82f875de6)(`[`SINGLYLINKEDLIST_HANDLE`](#singlylinkedlist_8h_1a355ba061e4132f7817d6d1963d33382a) list,`[`LIST_ACTION_FUNCTION`](#singlylinkedlist_8h_1ad849e7f533b60f38ce0f4dda3383cb7b) action_function,const void * action_context)`

