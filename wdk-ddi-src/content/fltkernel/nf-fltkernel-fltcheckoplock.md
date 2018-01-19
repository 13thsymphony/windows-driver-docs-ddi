---
UID : NF:fltkernel.FltCheckOplock
title : FltCheckOplock function
author : windows-driver-content
description : A minifilter driver calls FltCheckOplock to synchronize the callback data structure for an IRP-based file I/O operation with the file's current opportunistic lock (oplock) state.
old-location : ifsk\fltcheckoplock.htm
old-project : ifsk
ms.assetid : d6d8c83d-ca89-440a-b6a1-7d384030f7da
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : FltCheckOplock
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
req.alt-api : FltCheckOplock
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
req.irql : <= APC_LEVEL
req.typenames : EXpsFontRestriction
---


# FltCheckOplock function
A minifilter driver calls <b>FltCheckOplock</b> to synchronize the callback data structure for an IRP-based file I/O operation with the file's current opportunistic lock (oplock) state.

## Syntax

````
FLT_PREOP_CALLBACK_STATUS FltCheckOplock(
  _In_     POPLOCK                                 Oplock,
  _In_     PFLT_CALLBACK_DATA                      CallbackData,
  _In_opt_ PVOID                                   Context,
  _In_opt_ PFLTOPLOCK_WAIT_COMPLETE_ROUTINE        WaitCompletionRoutine,
  _In_opt_ PFLTOPLOCK_PREPOST_CALLBACKDATA_ROUTINE PrePostCallbackDataRoutine
);
````

## Parameters

`Oplock`

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>.

`CallbackData`

A pointer to the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for the I/O operation.

`Context`

A pointer to caller-defined context information to be passed to the callback routines that  <i>WaitCompletionRoutine</i> and <i>PrePostCallbackDataRoutine </i>point to. The Filter Manager treats this information as opaque.

`WaitCompletionRoutine`

A pointer to a caller-supplied callback routine. If an oplock break is in progress, the Filter Manager calls this routine when the oplock break is completed. This parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, the caller is put into a wait state until the oplock break is completed. 

This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*PFLTOPLOCK_WAIT_COMPLETE_ROUTINE) (
      IN PFLT_CALLBACK_DATA CallbackData,
      IN PVOID Context
      );</pre>
</td>
</tr>
</table></span></div>
This routine has the following parameters:

`PrePostCallbackDataRoutine`

A pointer to a caller-supplied callback routine to be called if the I/O operation is posted to a work queue. This parameter is optional and can be <b>NULL</b>. 

This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*PFLTOPLOCK_PREPOST_CALLBACKDATA_ROUTINE) (
      IN PFLT_CALLBACK_DATA CallbackData,
      IN PVOID Context
      );</pre>
</td>
</tr>
</table></span></div>


## Return Value

<b>FltCheckOplock</b> returns one of the following FLT_PREOP_CALLBACK_STATUS codes: 
<dl>
<dt><b>FLT_PREOP_COMPLETE</b></dt>
</dl><b>FltCheckOplock</b> encountered a pool allocation failure, or a call to the <a href="..\rxprocs\nf-rxprocs-fsrtlcheckoplock.md">FsRtlCheckOplock</a> function returned an error. <b>FltCheckOplock</b> will set the error code in the <b>Status</b> member of the <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure of the <b>IoStatus</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> callback data structure. The <i>CallbackData</i> parameter points to this FLT_CALLBACK_DATA. 
<dl>
<dt><b>FLT_PREOP_PENDING</b></dt>
</dl>An oplock break was initiated, which caused the Filter Manager to post the I/O operation to a work queue. The I/O operation is represented by the callback data that the <i>CallbackData</i> parameter points to. 
<dl>
<dt><b>FLT_PREOP_SUCCESS_WITH_CALLBACK</b></dt>
</dl>The I/O operation was performed immediately. Be aware that if this operation was a create operation that specified FILE_COMPLETE_IF_OPLOCKED in the create-options parameter, there might actually be an oplock break in progress even though the operation was performed immediately. To determine whether this is the situation, the caller should check the status in the <b>Status</b> member of the <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure of the <b>IoStatus</b> member of the <a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a> callback data structure.

## Remarks

A minifilter driver calls <b>FltCheckOplock</b> to synchronize an IRP-based I/O operation with the current oplock state of a file according to the following conditions: 

If the I/O operation will cause the oplock to break, the oplock break is initiated. 

If the I/O operation cannot continue until the oplock break is complete, <b>FltCheckOplock</b> returns FLT_PREOP_PENDING and calls the callback routine that the <i>PrePostCallbackDataRoutine</i> parameter points to. 

If a minifilter driver uses oplocks, it must call <b>FltCheckOplock</b> from any preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) routines for I/O operations that can cause oplock breaks. This rule applies to the following types of I/O operations, because these operations can cause oplock breaks: 

IRP_MJ_CLEANUP

IRP_MJ_CREATE

IRP_MJ_FILE_SYSTEM_CONTROL

IRP_MJ_FLUSH_BUFFERS

IRP_MJ_LOCK_CONTROL

IRP_MJ_READ

IRP_MJ_SET_INFORMATION

IRP_MJ_WRITE

The I/O operation must be an IRP-based I/O operation. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

Minifilters must not call <b>FltCheckOplock</b> again within the callback specified in <i>WaitCompletionRoutine</i>. Doing so can result in a deadlock condition if the oplock package calls the completion callback before <b>FltCheckOplock</b> returns.

For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcheckoplockex.md">FltCheckOplockEx</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcurrentbatchoplock.md">FltCurrentBatchOplock</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltoplockfsctrl.md">FltOplockFsctrl</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltoplockisfastiopossible.md">FltOplockIsFastIoPossible</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltuninitializeoplock.md">FltUninitializeOplock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-fsrtlcheckoplock.md">FsRtlCheckOplock</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCheckOplock function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>