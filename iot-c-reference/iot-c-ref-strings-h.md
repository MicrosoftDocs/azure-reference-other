# Header file strings.h 

Stub comment for brief. Please update this comment.

## Includes

\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  
\#include ["azure_c_shared_utility/strings_types.h"](iot-c-ref-strings-types-h.md)  
\#include <stddef.h>  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[STRING_new](./iot-c-ref-strings-h/string-new.md)            | 
[STRING_clone](./iot-c-ref-strings-h/string-clone.md)            | 
[STRING_construct](./iot-c-ref-strings-h/string-construct.md)            | 
[STRING_construct_n](./iot-c-ref-strings-h/string-construct-n.md)            | 
[STRING_new_with_memory](./iot-c-ref-strings-h/string-new-with-memory.md)            | 
[STRING_new_quoted](./iot-c-ref-strings-h/string-new-quoted.md)            | 
[STRING_new_JSON](./iot-c-ref-strings-h/string-new-json.md)            | 
[STRING_from_byte_array](./iot-c-ref-strings-h/string-from-byte-array.md)            | 
[STRING_delete](./iot-c-ref-strings-h/string-delete.md)            | 
[STRING_concat](./iot-c-ref-strings-h/string-concat.md)            | 
[STRING_concat_with_STRING](./iot-c-ref-strings-h/string-concat-with-string.md)            | 
[STRING_quote](./iot-c-ref-strings-h/string-quote.md)            | 
[STRING_copy](./iot-c-ref-strings-h/string-copy.md)            | 
[STRING_copy_n](./iot-c-ref-strings-h/string-copy-n.md)            | 
[STRING_c_str](./iot-c-ref-strings-h/string-c-str.md)            | 
[STRING_empty](./iot-c-ref-strings-h/string-empty.md)            | 
[STRING_length](./iot-c-ref-strings-h/string-length.md)            | 
[STRING_compare](./iot-c-ref-strings-h/string-compare.md)            | 
[STRING_replace](./iot-c-ref-strings-h/string-replace.md)            | 
[STRING_construct_sprintf](./iot-c-ref-strings-h/string-construct-sprintf.md)            | 
[STRING_sprintf](./iot-c-ref-strings-h/string-sprintf.md)            | 

## Function documentation

#### STRING_new 
[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) `[`STRING_new`](#strings_8h_1ade72be627db6a28a2efe5c0340ae47b3)(void)`

#### STRING_clone 
[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) `[`STRING_clone`](#strings_8h_1ac700e7a0a099bc7ac42abba74b9fd874)(`[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) handle)`

#### STRING_construct 
[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) `[`STRING_construct`](#strings_8h_1ad091a0c95f3dcf64d9f0c242744b464d)(const char * psz)`

#### STRING_construct_n 
[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) `[`STRING_construct_n`](#strings_8h_1a83782be1165db064604a3be0db0474e8)(const char * psz,size_t n)`

#### STRING_new_with_memory 
[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) `[`STRING_new_with_memory`](#strings_8h_1abb0b2550bd2c7bb2479c51bead3c66df)(const char * memory)`

#### STRING_new_quoted 
[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) `[`STRING_new_quoted`](#strings_8h_1aa20efc350f074188ca1dc6c35d1289b9)(const char * source)`

#### STRING_new_JSON 
[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) `[`STRING_new_JSON`](#strings_8h_1a036cafbe83b5cd817a576bc7b72da187)(const char * source)`

#### STRING_from_byte_array 
[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) `[`STRING_from_byte_array`](#strings_8h_1a64e30b6f4b9a2deb6a6a36185383e774)(const unsigned char * source,size_t size)`

#### STRING_delete 
void `[`STRING_delete`](#strings_8h_1a14f1a6a01de229149d3810d4d06816a2)(`[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) handle)`

#### STRING_concat 
int `[`STRING_concat`](#strings_8h_1ae97f94b5ef464ef7b5fdcf0fb6eb6bf1)(`[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) handle,const char * s2)`

#### STRING_concat_with_STRING 
int `[`STRING_concat_with_STRING`](#strings_8h_1aa4a3f5638a574f7dfad01419df072e2a)(`[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) s1,`[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) s2)`

#### STRING_quote 
int `[`STRING_quote`](#strings_8h_1aeb9ea76e7a83a72ddb5b44276fc3ea6f)(`[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) handle)`

#### STRING_copy 
int `[`STRING_copy`](#strings_8h_1a4ac1d23e4802a5246478551febe0ff91)(`[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) s1,const char * s2)`

#### STRING_copy_n 
int `[`STRING_copy_n`](#strings_8h_1a0c83d32c878fc5d3153d6323480b8860)(`[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) s1,const char * s2,size_t n)`

#### STRING_c_str 
const char * `[`STRING_c_str`](#strings_8h_1a351a84891e778e497c7eafa76bd02cd0)(`[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) handle)`

#### STRING_empty 
int `[`STRING_empty`](#strings_8h_1a6f94f5fb132262e04f8f3d6fb4909d9d)(`[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) handle)`

#### STRING_length 
size_t `[`STRING_length`](#strings_8h_1ad5dac28de3fdf01777ac937fa876ac3c)(`[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) handle)`

#### STRING_compare 
int `[`STRING_compare`](#strings_8h_1a9b62eac68483a4bfc490dfe7825ef7f3)(`[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) s1,`[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) s2)`

#### STRING_replace 
int `[`STRING_replace`](#strings_8h_1ab375792533e3a1261e8aed4c4c104295)(`[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) handle,char target,char replace)`

#### STRING_construct_sprintf 
[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) `[`STRING_construct_sprintf`](#strings_8h_1ab3f670a1274ad8b1a721599e19166c6c)(const char * format,...)`

#### STRING_sprintf 
int `[`STRING_sprintf`](#strings_8h_1ab164a927aa4332e08b3698398beb3861)(`[`STRING_HANDLE`](#strings__types_8h_1a38c89d91aecbdc355555337b6eb88dbf) s1,const char * format,...)`

