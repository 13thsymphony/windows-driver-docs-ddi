---
UID: NF.fltkernel.FltCheckOplockEx
title: FltCheckOplockEx function
author: windows-driver-content
description: A minifilter driver calls the FltCheckOplockEx routine to synchronize the callback data structure for an IRP-based file I/O operation that has the current opportunistic lock (oplock) state of the file.
old-location: ifsk\fltcheckoplockex.htm
old-project: ifsk
ms.assetid: 2af1f496-48cf-4f99-a22b-cf7d1837617e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FltCheckOplockEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: The FltCheckOplockEx routine is available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltCheckOplockEx
req.alt-loc: FltMgr.lib,FltMgr.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: 
req.irql: <= APC_LEVEL
---

# FltCheckOplockEx function



## -description
A minifilter driver calls the <b>FltCheckOplockEx</b> routine to synchronize the callback data structure for an IRP-based file I/O operation that has the current opportunistic lock (oplock) state of the file. 



## -syntax

````
FLT_PREOP_CALLBACK_STATUS FltCheckOplockEx(
  _In_     POPLOCK                                 Oplock,
  _In_     PFLT_CALLBACK_DATA                      CallbackData,
  _In_     ULONG                                   Flags,
  _In_opt_ PVOID                                   Context,
  _In_opt_ PFLTOPLOCK_WAIT_COMPLETE_ROUTINE        WaitCompletionRoutine,
  _In_opt_ PFLTOPLOCK_PREPOST_CALLBACKDATA_ROUTINE PrePostCallbackDataRoutine
);
````


## -parameters

### -param Oplock [in]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="ifsk.fltinitializeoplock">FltInitializeOplock</a>. 


### -param CallbackData [in]

A pointer to the callback data (<a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a>) structure for the I/O operation. 


### -param Flags [in]

A bitmask for the associated file I/O operation. A minifilter driver sets bits to specify the behavior of <b>FltCheckOplockEx</b>. The <i>Flags</i> parameter has the following options:




### -param OPLOCK_FLAG_COMPLETE_IF_OPLOCKED (0x00000001)

Allows an opportunistic lock break to proceed without blocking or pending the operation that caused the oplock break. 


### -param OPLOCK_FLAG_OPLOCK_KEY_CHECK_ONLY (0x00000002)

Specifies that <b>FltCheckOplockEx</b> should only check for an opportunistic lock key on the FILE_OBJECT that is associated with the I/O operation. This I/O operations is represented by the callback data that the <i>CallbackData</i> parameter points to. <b>FltCheckOplockEx </b>must then add the key if one is provided in the I/O operation. No other oplock processing occurs; that is, no opportunistic lock break will occur. 


### -param OPLOCK_FLAG_BACK_OUT_ATOMIC_OPLOCK (0x00000004)

Specifies that <a href="ifsk.fsrtlcheckoplockex">FsRtlCheckOplockEx</a> should revert any state that was previously set up through a call to the <a href="ifsk.fltoplockfsctrl">FltOplockFsctrl</a> routine. <b>FltOplockFsctrl</b> is called when an IRP_MJ_CREATE request is processed. This IRP_MJ_CREATE request specifies the FILE_OPEN_REQUIRING_OPLOCK flag in the create options parameter. The OPLOCK_FLAG_BACK_OUT_ATOMIC_OPLOCK flag is typically used in final processing of such a create request when it previously failed. 


### -param OPLOCK_FLAG_IGNORE_OPLOCK_KEYS (0x00000008)

Allows all opportunistic lock breaks to proceed regardless of the opportunistic lock key. 

</dd>
</dl>

### -param Context [in, optional]

A pointer to caller-defined context information to be passed to the callback routines that <i>WaitCompletionRoutine</i> and <i>PrePostCallbackDataRoutine </i>point to. The Filter Manager treats this information as opaque. 


### -param WaitCompletionRoutine [in, optional]

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




### -param CallbackData

A pointer to the callback data structure for the I/O operation. 


### -param Context

A context information pointer that was passed in the <i>Context</i> parameter to <b>FltCheckOplockEx</b>. 

</dd>
</dl>

### -param PrePostCallbackDataRoutine [in, optional]

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



### -param CallbackData

A pointer to the callback data structure for the I/O operation. 


### -param Context

A context information pointer that was passed in the <i>Context</i> parameter to <b>FltCheckOplockEx</b>. 

</dd>
</dl>

## -returns
<b>FltCheckOplockEx</b> returns one of the following FLT_PREOP_CALLBACK_STATUS codes: 
<dl>
<dt><b>FLT_PREOP_COMPLETE</b></dt>
</dl><b>FltCheckOplockEx</b> encountered a pool allocation failure, or a call to the <a href="ifsk.fsrtlcheckoplockex">FsRtlCheckOplockEx</a> function returned an error. <b>FltCheckOplockEx</b> sets the error code in the <b>Status</b> member of the <a href="kernel.io_status_block">IO_STATUS_BLOCK</a> structure of the <b>IoStatus</b> member of the <a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a> callback data structure. The <i>CallbackData</i> parameter points to this FLT_CALLBACK_DATA structure. 
<dl>
<dt><b>FLT_PREOP_PENDING</b></dt>
</dl>An oplock break was initiated, which caused the Filter Manager to post the I/O operation to a work queue. The I/O operation is represented by the callback data that the <i>CallbackData</i> parameter points to. 
<dl>
<dt><b>FLT_PREOP_SUCCESS_WITH_CALLBACK</b></dt>
</dl>The callback data that the <i>CallbackData</i> parameter points to was not pended, and the I/O operation was performed immediately. Be aware that if the caller specified OPLOCK_FLAG_COMPLETE_IF_OPLOCKED in the <i>Flags</i> parameter, an oplock break might actually be in progress even though the I/O operation was not pended. To determine whether this is the situation, the caller should check for STATUS_OPLOCK_BREAK_IN_PROGRESS in the <b>Status</b> member of the <a href="kernel.io_status_block">IO_STATUS_BLOCK</a> structure of the <b>IoStatus</b> member of the <a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a> callback data structure. 

 


## -remarks
A minifilter driver calls <b>FltCheckOplockEx</b> to synchronize an IRP-based I/O operation with the current oplock state of a file according to the following conditions: 

If the I/O operation will cause the oplock to break, the oplock break is initiated. 

If the I/O operation cannot continue until the oplock break is complete, <b>FltCheckOplockEx</b> returns FLT_PREOP_PENDING and calls the callback routine that the <i>PrePostCallbackDataRoutine</i> parameter points to. 

If a minifilter driver uses oplocks, it must call <b>FltCheckOplockEx</b> from any preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) routine for I/O operations that can cause oplock breaks. This rule applies to the following types of I/O operations, because these operations can cause oplock breaks: 

IRP_MJ_CLEANUP

IRP_MJ_CREATE

IRP_MJ_FILE_SYSTEM_CONTROL

IRP_MJ_FLUSH_BUFFERS

IRP_MJ_LOCK_CONTROL

IRP_MJ_READ

IRP_MJ_SET_INFORMATION

IRP_MJ_WRITE

The I/O operation must be an IRP-based I/O operation. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

Minifilters must not call <b>FltCheckOplockEx</b> again within the callback specified in <i>WaitCompletionRoutine</i>. Doing so can result in a deadlock condition if the oplock package calls the completion callback before <b>FltCheckOplockEx</b> returns.

For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
The <b>FltCheckOplockEx</b> routine is available starting with Windows 7. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>
</dt>
<dt>
<a href="ifsk.fltinitializeoplock">FltInitializeOplock</a>
</dt>
<dt>
<a href="ifsk.fltoplockfsctrl">FltOplockFsctrl</a>
</dt>
<dt>
<a href="ifsk.fsrtlcheckoplockex">FsRtlCheckOplockEx</a>
</dt>
<dt>
<a href="kernel.io_status_block">IO_STATUS_BLOCK</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltCheckOplockEx routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

