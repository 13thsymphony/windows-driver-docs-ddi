---
UID : NS:strmini._HW_CLOCK_OBJECT
title : _HW_CLOCK_OBJECT
author : windows-driver-content
description : The HW_CLOCK_OBJECT structure describes the clock associated with a stream.
old-location : stream\hw_clock_object.htm
old-project : stream
ms.assetid : d6afe946-90cb-4b17-94ed-2e7c508985a3
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : _HW_CLOCK_OBJECT, HW_CLOCK_OBJECT, *PHW_CLOCK_OBJECT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : strmini.h
req.include-header : Strmini.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : HW_CLOCK_OBJECT
req.alt-loc : strmini.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : HW_CLOCK_OBJECT, *PHW_CLOCK_OBJECT
req.product : Windows 10 or later.
---

# _HW_CLOCK_OBJECT structure
The HW_CLOCK_OBJECT structure describes the clock associated with a stream.

## Syntax
````
typedef struct _HW_CLOCK_OBJECT {
  PHW_CLOCK_FUNCTION HwClockFunction;
  ULONG              ClockSupportFlags;
  ULONG              Reserved[2];
} HW_CLOCK_OBJECT, *PHW_CLOCK_OBJECT;
````

## Members

        
            `ClockSupportFlags`

            Specifies which options the <i>StrMiniClock</i> routine supports.
        
            `HwClockFunction`

            Pointer to the stream's <a href="https://msdn.microsoft.com/library/windows/hardware/ff568452">StrMiniClock</a> routine.
        
            `Reserved`

            Reserved for system use. Do not use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | strmini.h (include Strmini.h) |

    ## See Also

        <dl>
<dt>
<a href="..\strmini\ns-strmini-_hw_stream_object.md">HW_STREAM_OBJECT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568452">StrMiniClock</a>
</dt>
<dt>
<a href="..\strmini\ns-strmini-_hw_time_context.md">HW_TIME_CONTEXT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20HW_CLOCK_OBJECT structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>