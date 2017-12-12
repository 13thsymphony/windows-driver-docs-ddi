---
UID: NF.fltkernel.FltProcessFileLock
title: FltProcessFileLock function
author: windows-driver-content
description: The FltProcessFileLock routine processes and completes a file lock operation.
old-location: ifsk\fltprocessfilelock.htm
old-project: ifsk
ms.assetid: 72b8aad8-39e1-4624-ac77-13eb52036b3b
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltProcessFileLock
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with  Windows XP with SP2 or Windows Server 2003 with SP1.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltProcessFileLock
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
---

# FltProcessFileLock function



## -description
The <b>FltProcessFileLock</b> routine processes and completes a file lock operation.



## -syntax

````
FLT_PREOP_CALLBACK_STATUS FltProcessFileLock(
  _In_     PFILE_LOCK         FileLock,
  _In_     PFLT_CALLBACK_DATA CallbackData,
  _In_opt_ PVOID              Context
);
````


## -parameters

### -param FileLock [in]

Pointer to the FILE_LOCK structure for the file. This structure must have been initialized by a previous call to <a href="ifsk.fltallocatefilelock">FltAllocateFileLock</a> or <a href="ifsk.fltinitializefilelock">FltInitializeFileLock</a>. 


### -param CallbackData [in]

Pointer to the callback data (<a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a>) structure for the <a href="ifsk.irp_mj_lock_control">IRP_MJ_LOCK_CONTROL</a> operation. 


### -param Context [in, optional]

Context pointer to be used when completing the operation. This context pointer is passed to the <i>CompleteLockCallbackDataRoutine</i> and <i>UnlockRoutine</i> callback routines that the minifilter driver registered in a previous call to <a href="ifsk.fltallocatefilelock">FltAllocateFileLock</a>. This parameter is optional and can be <b>NULL</b>. 


## -returns
<b>FltProcessFileLock</b> returns one of the following. 
<dl>
<dt><b>FLT_PREOP_COMPLETE</b></dt>
</dl>The Filter Manager is done with the <i>CallbackData</i>, which can now be completed. 
<dl>
<dt><b>FLT_PREOP_DISALLOW_FASTIO</b></dt>
</dl>The <i>CallbackData</i> represents a fast I/O operation, and a minifilter driver in the stack has disallowed the fast I/O to be used for this operation. The Filter Manager does not send the operation to any minifilter drivers below the one that disallowed the operation. In this case, the Filter Manager only calls the postoperation callback routines (and <i>CompleteLockCallbackDataRoutine</i> callbacks) of the minifilter drivers above the minifilter driver that disallowed the fast I/O operation. 
<dl>
<dt><b>FLT_PREOP_PENDING</b></dt>
</dl>The lock operation has been pended. 

 


## -remarks
<b>FltProcessFileLock</b> processes a file lock (<a href="ifsk.irp_mj_lock_control">IRP_MJ_LOCK_CONTROL</a>) operation. The lock operation can be a fast I/O or IRP-based operation. 

For unlock operations, the Filter Manager calls the <i>UnlockRoutine</i> (<a href="ifsk.punlock_routine">PUNLOCK_ROUTINE</a>) callback routine that the caller registered for the <a href="ifsk.file_lock">FILE_LOCK</a> structure in a previous call to <a href="ifsk.fltallocatefilelock">FltAllocateFileLock</a>. 

When the lock operation is completed, the Filter Manager calls the <i>CompleteLockCallbackDataRoutine</i> (<a href="..\fltkernel\nc-fltkernel-pflt_complete_lock_callback_data_routine.md">PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE</a>) completion callback routine that the caller registered for the <a href="ifsk.file_lock">FILE_LOCK</a> structure in a previous call to <a href="ifsk.fltallocatefilelock">FltAllocateFileLock</a>. 

When the <i>CallbackData</i> parameter passed to <b>FltProcessFileLock</b> represents a fast I/O operation, the callback specified in <i>CompleteLockCallbackDataRoutine</i> parameter of the <a href="ifsk.fltallocatefilelock">FltAllocateFileLock</a> routine is not invoked. Only when the I/O operation in <i>CallbackData</i> is an IRP, and <i>CompleteLockCallbackDataRoutine</i> is not NULL, will the callback routine be called.

To determine whether the <i>CallbackData</i> represents a fast I/O operation, use the <a href="ifsk.flt_is_fastio_operation">FLT_IS_FASTIO_OPERATION</a> macro. 

To allocate and initialize a new file lock structure, call <a href="ifsk.fltallocatefilelock">FltAllocateFileLock</a>. 

To free an initialized<a href="ifsk.file_lock">FILE_LOCK</a> structure, call <a href="ifsk.fltfreefilelock">FltFreeFileLock</a>



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
Available starting with  Windows XP with SP2 or Windows Server 2003 with SP1.

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
DLL

</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
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
<a href="ifsk.file_lock">FILE_LOCK</a>
</dt>
<dt>
<a href="ifsk.flt_callback_data">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="ifsk.flt_is_fastio_operation">FLT_IS_FASTIO_OPERATION</a>
</dt>
<dt>
<a href="ifsk.fltallocatefilelock">FltAllocateFileLock</a>
</dt>
<dt>
<a href="ifsk.fltchecklockforreadaccess">FltCheckLockForReadAccess</a>
</dt>
<dt>
<a href="ifsk.fltchecklockforwriteaccess">FltCheckLockForWriteAccess</a>
</dt>
<dt>
<a href="ifsk.fltfreefilelock">FltFreeFileLock</a>
</dt>
<dt>
<a href="ifsk.fltinitializefilelock">FltInitializeFileLock</a>
</dt>
<dt>
<a href="ifsk.fltuninitializefilelock">FltUninitializeFileLock</a>
</dt>
<dt>
<a href="ifsk.fsrtlprocessfilelock">FsRtlProcessFileLock</a>
</dt>
<dt>
<a href="ifsk.irp_mj_lock_control">IRP_MJ_LOCK_CONTROL</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_complete_lock_callback_data_routine.md">PFLT_COMPLETE_LOCK_CALLBACK_DATA_ROUTINE</a>
</dt>
<dt>
<a href="ifsk.punlock_routine">PUNLOCK_ROUTINE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltProcessFileLock routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

