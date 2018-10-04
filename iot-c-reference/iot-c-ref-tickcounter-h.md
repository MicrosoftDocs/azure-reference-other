# Header file tickcounter.h 

Stub comment for brief. Please update this comment.

## Includes

\#include <stdint.h>  
\#include ["azure_c_shared_utility/umock_c_prod.h"](iot-c-ref-umock-c-prod-h.md)  

## Detailed Description

Stub comment for details. Please update this comment.

## Functions

Function Name                  | Description                                
--------------------------------|---------------------------------------------
[tickcounter_create](./iot-c-ref-tickcounter-h/tickcounter-create.md)            | 
[tickcounter_destroy](./iot-c-ref-tickcounter-h/tickcounter-destroy.md)            | 
[tickcounter_get_current_ms](./iot-c-ref-tickcounter-h/tickcounter-get-current-ms.md)            | 

## Typedefs

Typedef                        | Value                                
--------------------------------|---------------------------------------------
tickcounter_ms_t            | 
TICK_COUNTER_HANDLE            | 

## Function documentation

#### tickcounter_create 
[TICK_COUNTER_HANDLE](#tickcounter_8h_1ae768079d7100885a5f7a14c1e474356a) [tickcounter_create](#tickcounter_8h_1a58975c98066c833f9a78ec40f8a9da51)(void)

#### tickcounter_destroy 
void [tickcounter_destroy](#tickcounter_8h_1a3e8011efd045ca7d0dcd23759578e5af)([TICK_COUNTER_HANDLE](#tickcounter_8h_1ae768079d7100885a5f7a14c1e474356a) tick_counter)

#### tickcounter_get_current_ms 
int [tickcounter_get_current_ms](#tickcounter_8h_1ae17afabcfd8497d6b95689f620ddac3a)([TICK_COUNTER_HANDLE](#tickcounter_8h_1ae768079d7100885a5f7a14c1e474356a) tick_counter,[tickcounter_ms_t](#tickcounter_8h_1a9ddfa2ac37b8109d6afb1f6432d651a7) * current_ms)

