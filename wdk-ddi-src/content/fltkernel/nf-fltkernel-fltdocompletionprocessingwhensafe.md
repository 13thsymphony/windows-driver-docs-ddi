---
UID : NF:fltkernel.FltDoCompletionProcessingWhenSafe
title : FltDoCompletionProcessingWhenSafe function
author : windows-driver-content
description : If it is safe to do so, the FltDoCompletionProcessingWhenSafe function executes a minifilter driver postoperation callback routine.
old-location : ifsk\fltdocompletionprocessingwhensafe.htm
old-project : ifsk
ms.assetid : 8143c741-8f6e-442d-a52a-c226b2e4aa57
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ifsk.fltdocompletionprocessingwhensafe, FltDoCompletionProcessingWhenSafe routine [Installable File System Drivers], FltApiRef_a_to_d_4e8cd7a1-1469-4ae1-97a9-51a184d0ad5a.xml, FltDoCompletionProcessingWhenSafe, fltkernel/FltDoCompletionProcessingWhenSafe
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fltkernel.h
req.include-header : Fltkernel.h
req.target-type : Universal
req.target-min-winverclnt : Available in Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Windows Server 2003 SP1, and later operating systems. Not available in Windows 2000 SP4 and earlier operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Fltmgr.lib
req.dll : 
req.irql : Any.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : EXpsFontRestriction
---


# FltDoCompletionProcessingWhenSafe function
If it is safe to do so, the <b>FltDoCompletionProcessingWhenSafe</b> function executes a minifilter driver postoperation callback routine.

## Syntax

````
BOOLEAN FltDoCompletionProcessingWhenSafe(
  _In_     PFLT_CALLBACK_DATA           Data,
  _In_     PCFLT_RELATED_OBJECTS        FltObjects,
  _In_opt_ PVOID                        CompletionContext,
  _In_     FLT_POST_OPERATION_FLAGS     Flags,
  _In_     PFLT_POST_OPERATION_CALLBACK SafePostCallback,
  _Out_    PFLT_POSTOP_CALLBACK_STATUS  RetPostOperationStatus
);
````

## Parameters

`Data`

Pointer to the callback data structure (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) for the I/O operation. Usually this is the same as the <i>Data</i> pointer that was passed to the postoperation callback routine (<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>) that called <b>FltDoCompletionProcessingWhenSafe</b>.

`FltObjects`

Pointer to the related objects structure (<a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a>) for the I/O operation. Usually this is the same as the <i>FltObjects</i> pointer that was passed to the postoperation callback routine that called <b>FltDoCompletionProcessingWhenSafe</b>.

`CompletionContext`

Pointer to a caller-supplied context information that will be passed in to the callback function that is specified in the <i>SafePostCallback</i> parameter.

`Flags`

Bitmask of flags which specify how completion processing will be performed. Usually this is the same as the <i>Flags</i> value that was passed to the postoperation callback routine that called <b>FltDoCompletionProcessingWhenSafe</b>. For more information, see the following Remarks section.

`SafePostCallback`

Pointer to a caller-supplied <a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>-typed callback routine that the operating system calls when it is safe to do so.

`RetPostOperationStatus`

Caller-allocated variable that receives the final status value for the I/O operation. For more information on how this parameter is set, see the following Remarks section.


## Return Value

<b>FltDoCompletionProcessingWhenSafe</b> returns <b>TRUE</b> if completion processing for the I/O operation can be performed immediately or the I/O operation was successfully posted to a worker thread; otherwise, it returns <b>FALSE</b>.

## Remarks

<b>FltDoCompletionProcessingWhenSafe</b> executes the <i>SafePostCallback</i> immediately if the caller is running at IRQL &lt;= APC_LEVEL. Otherwise, if it is safe to post the operation to a worker thread, the <i>SafePostCallback</i> processing is deferred until it can be called in a thread context where IRQL &lt;= APC_LEVEL.

If IRQL &lt; DISPATCH_LEVEL:
<ul>
<li>
<b>FltDoCompletionProcessingWhenSafe </b>calls the callback routine specified in <i>SafePostCallback</i>.

</li>
<li>
The <i>RetPostOperationStatus</i> parameter receives a FLT_POSTOP_CALLBACK_STATUS value returned by <i>SafePostCallback</i>.

</li>
<li>
<b>FltDoCompletionProcessingWhenSafe</b> returns <b>TRUE</b>.

</li>
</ul>If IRQL &gt;= DISPATCH_LEVEL, <b>FltDoCompletionProcessingWhenSafe</b> attempts to post the I/O operation to a worker thread. 
<ul>
<li><b>FltDoCompletionProcessingWhenSafe </b>calls the <i>SafePostCallback</i> routine from the worker thread.</li>
<li> Filter manager sets <i>RetPostOperationStatus</i> to FLT_POSTOP_MORE_PROCESSING_REQUIRED.</li>
<li><b>FltDoCompletionProcessingWhenSafe</b> returns <b>TRUE</b>.</li>
</ul><ul>
<li>Filter manager sets <i>RetPostOperationStatus</i> to FLT_POSTOP_FINISHED_PROCESSING.</li>
<li><b>FltDoCompletionProcessingWhenSafe</b> returns <b>FALSE</b>.</li>
</ul><b>FltDoCompletionProcessingWhenSafe</b> can only be called for IRP-based operations. To determine whether the operation is an IRP-based operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

<b>FltDoCompletionProcessingWhenSafe</b> cannot be used to post completion of a paging I/O operation to a worker thread.

<b>FltDoCompletionProcessingWhenSafe</b> can only be called from a minifilter driver's postoperation callback routine (<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>). Note that <b>FltDoCompletionProcessingWhenSafe</b> should never be called if the <i>Flags</i> parameter of the postoperation callback has the FLTFL_POST_OPERATION_DRAINING bit set. 

If a minifilter calls <b>FltDoCompletionProcessingWhenSafe</b> and the <i>SafePostCallback</i> is invoked in a worker thread because it is not safe to invoke it in the current thread context, the filter manager will resume completion processing as long as the minifilter does not return FLT_POSTOP_MORE_PROCESSING_REQUIRED from the <i>SafePostCallback</i>.

If the minifilter does return FLT_POSTOP_MORE_PROCESSING_REQUIRED from the <i>SafePostCallback</i>, the minifilter must call <a href="..\fltkernel\nf-fltkernel-fltcompletependedpostoperation.md">FltCompletePendedPostOperation</a> to resume completion processing.
<div class="alert"><b>Caution</b>    To avoid deadlocks, <b>FltDoCompletionProcessingWhenSafe</b> cannot be called for I/O operations that can be directly completed by a driver in the storage stack, such as the following:<dl>
<dd>
<ul>
<li> IRP_MJ_READ</li>
<li> IRP_MJ_WRITE</li>
<li> IRP_MJ_FLUSH_BUFFERS</li>
</ul>
</dd>
</dl>
</div><div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** |  |
| **IRQL** | Any. |
| **DDI compliance rules** |  |

## See Also

<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>

<a href="..\fltkernel\ns-fltkernel-_flt_related_objects.md">FLT_RELATED_OBJECTS</a>

<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>

<a href="..\fltkernel\nf-fltkernel-fltcompletependedpostoperation.md">FltCompletePendedPostOperation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>

<a href="..\fltkernel\nf-fltkernel-fltcancelio.md">FltCancelIo</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltDoCompletionProcessingWhenSafe routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>