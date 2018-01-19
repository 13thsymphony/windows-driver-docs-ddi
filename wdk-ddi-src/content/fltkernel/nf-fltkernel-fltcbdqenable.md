---
UID : NF:fltkernel.FltCbdqEnable
title : FltCbdqEnable function
author : windows-driver-content
description : FltCbdqEnable enables a callback data queue that was disabled by a previous call to FltCbdqDisable.
old-location : ifsk\fltcbdqenable.htm
old-project : ifsk
ms.assetid : cc9167cc-366e-4824-9968-1e2895a61a0c
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : FltCbdqEnable
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fltkernel.h
req.include-header : Fltkernel.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : FltCbdqEnable
req.alt-loc : fltkernel.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : See Remarks section
req.typenames : EXpsFontRestriction
---


# FltCbdqEnable function
<i>FltCbdqEnable</i> enables a callback data queue that was disabled by a previous call to <a href="..\fltkernel\nf-fltkernel-fltcbdqdisable.md">FltCbdqDisable</a>.

## Syntax

````
VOID FltCbdqEnable(
  _Inout_ PFLT_CALLBACK_DATA_QUEUE Cbdq
);
````

## Parameters

`Cbdq`

Pointer to the callback data queue.


## Return Value

None

## Remarks

<i>FltCbdqEnable</i> reenables a callback data queue that was disabled by a previous call to <a href="..\fltkernel\nf-fltkernel-fltcbdqdisable.md">FltCbdqDisable</a>. After the callback data queue is reenabled, it can once again accept new items. 

Minifilter drivers can use the <b>FltCbdq</b><i>Xxx</i> routines to implement a callback data queue for IRP-based I/O operations. By using these routines, minifilter drivers can make their queue cancel-safe; the system transparently handles I/O cancellation for the minifilter driver. 

The <b>FltCbdq</b><i>Xxx</i> routines can only be used for IRP-based I/O operations. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

If the queue is protected by a <a href="https://msdn.microsoft.com/0585fc2a-0d0b-434d-92b3-da07a9385444">spin lock</a> rather than a <a href="https://msdn.microsoft.com/e2142b6d-f460-4f80-be0f-e00b5d43731c">mutex object</a> or <a href="..\wdm\nf-wdm-exinitializeresourcelite.md">resource variable</a>, the caller of <i>FltCbdqEnable</i> can be running at IRQL &lt;= DISPATCH_LEVEL. If a mutex or resource is used, the caller must be running at IRQL &lt;= APC_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** |  |
| **IRQL** | See Remarks section |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_callback_data_queue.md">FLT_CALLBACK_DATA_QUEUE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcbdqdisable.md">FltCbdqDisable</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcbdqinitialize.md">FltCbdqInitialize</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcbdqinsertio.md">FltCbdqInsertIo</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcbdqremoveio.md">FltCbdqRemoveIo</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcbdqremovenextio.md">FltCbdqRemoveNextIo</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCbdqEnable function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>