# tlsio.h 

Stub comment for brief. Please update this comment.

## Includes

\#include "[xio.h](iot-c-ref-xio-h.md)"  

## Detailed Description

Stub comment for details. Please update this comment.

## Structures

#### TLSIO_CONFIG

```C
struct TLSIO_CONFIG {
  const char *                                                                                                                                                                                                                                                                                                                                              hostname,
  int                                                                                                                                                                                                                                                                                                                                                       port,
  const [IO_INTERFACE_DESCRIPTION](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    }) *  underlying_io_interface,
  void *                                                                                                                                                                                                                                                                                                                                                    underlying_io_parameters
};
```
Member name                 | Description                                
----------------------------|----------------
 hostname            | 
 port            | 
 underlying_io_interface            | 
 underlying_io_parameters            | 

