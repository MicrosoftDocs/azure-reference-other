# ThreadAPI_Exit()

This function is called by a thread when the thread exits.

## Syntax

\#include "[azure-iot-sdk-c/c-utility/inc/azure_c_shared_utility/threadapi.h](../iot-c-ref-threadapi-h.md)"  
```C
void ThreadAPI_Exit(
  int  res
);
```

## Parameters
* `res` An integer that represents the exit status of the thread.

This function is called by a thread when the thread exits in order to return a result value to the caller of the [ThreadAPI_Join](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    }) function. The `res` value must be copied into the `res` out argument passed to the [ThreadAPI_Join](function (refid) {
      if ((options.groups || options.classes) && compound.refid !== refid && references[refid]) {
        return util.format(options.output, options.groups ? references[refid].groupname : references[refid].name) + '#' + refid;
      } else {
        return '#' + refid;
      }
    }) function.

