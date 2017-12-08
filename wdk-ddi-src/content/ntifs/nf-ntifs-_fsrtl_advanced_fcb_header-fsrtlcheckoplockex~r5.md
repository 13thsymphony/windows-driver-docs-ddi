---
UID: NF.ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlCheckOplockEx~r5
title: FsRtlCheckOplockEx function
author: windows-driver-content
description: The FsRtlCheckOplockEx routine synchronizes the IRP for a file I/O operation with the current opportunistic lock (oplock) state of the file.
old-location: ifsk\fsrtlcheckoplockex.htm
old-project: ifsk
ms.assetid: e06ae137-fbd8-47cc-8102-9fe21993f1ca
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FsRtlCheckOplockEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlCheckOplockEx routine is available starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlCheckOplockEx
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
---

# FsRtlCheckOplockEx function



## -description
The <b>FsRtlCheckOplockEx</b> routine synchronizes the IRP for a file I/O operation with the current opportunistic lock (oplock) state of the file. 


## -syntax

````
NTSTATUS FsRtlCheckOplockEx(
  _In_     POPLOCK                       Oplock,
  _In_     PIRP                          Irp,
  _In_     ULONG                         Flags,
  _In_opt_ PVOID                         Context,
  _In_opt_ POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine,
  _In_opt_ POPLOCK_FS_PREPOST_IRP        PostIrpRoutine
);
````


## -parameters

### -param Oplock [in]

A opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="ifsk.fsrtlinitializeoplock">FsRtlInitializeOplock</a>. 

### -param Irp [in]

A pointer to the IRP for the I/O operation. 

### -param Flags [in]

A bitmask for the associated file I/O operation. A file system or filter driver sets bits to specify the behavior of <b>FsRtlCheckOplockEx</b>. The <i>Flags</i> parameter has the following options:


### -param OPLOCK_FLAG_COMPLETE_IF_OPLOCKED (0x00000001)

Specifies to allow an opportunistic lock break to proceed without blocking or pending the operation that caused the oplock break. 

### -param OPLOCK_FLAG_OPLOCK_KEY_CHECK_ONLY (0x00000002)

Supported starting with Windows 7.
Specifies that <b>FsRtlCheckOplockEx</b> should only check for an opportunistic lock key on the FILE_OBJECT that is associated with the IRP that the <i>Irp</i> parameter points to. <b>FsRtlCheckOplockEx</b> must then add the key if one is provided in the IRP. No other oplock processing occurs; that is, no opportunistic lock break will occur. 

### -param OPLOCK_FLAG_BACK_OUT_ATOMIC_OPLOCK (0x00000004)

Supported starting with Windows 7.
Specifies that <b>FsRtlCheckOplockEx</b> should revert any state that was previously set up through a call to the <a href="ifsk.fsrtloplockfsctrl">FsRtlOplockFsctrl</a> routine. <b>FsRtlOplockFsctrl</b> is called during processing of an IRP_MJ_CREATE request that specifies the FILE_OPEN_REQUIRING_OPLOCK flag in the create options parameter. The OPLOCK_FLAG_BACK_OUT_ATOMIC_OPLOCK flag is typically used in final processing of such a create request when it previously failed. 

### -param OPLOCK_FLAG_IGNORE_OPLOCK_KEYS (0x00000008)

Supported starting with Windows 7.
Specifies to allow all opportunistic lock breaks to proceed regardless of the opportunistic lock key. 

### -param OPLOCK_FLAG_PARENT_OBJECT (0x00000010)

Supported starting with Windows 8.
Specifies that <i>Oplock</i> is associated with the parent (directory) of the file or directory to which the IRP in the <i>Irp</i> parameter is directed.

### -param OPLOCK_FLAG_CLOSING_DELETE_ON_CLOSE (0x00000020)

Supported starting with Windows 8.
Specifies that the I/O operation specified in <i>Irp</i> is an IRP_MJ_CLEANUP for a handle that was originally opened with the FILE_DELETE_ON_CLOSE flag set in its create options.  This flag as no effect if <i>Irp</i> is not an IRP_MJ_CLEANUP operation.  Specifying this flag may result in an opportunistic lock break.

### -param OPLOCK_FLAG_REMOVING_FILE_OR_LINK   (0x00000040)

Supported starting with Windows 8.
Specifies handling an opportunistic lock break on a parent directory when deleting a file or link in that directory. If specified, this flag must be combined with OPLOCK_FLAG_PARENT_OBJECT.  This flag must be specified when the file system is processing an operation that results in the removal of a link or file.
</dd>
</dl>

### -param Context [in, optional]

A pointer to caller-defined context information to be passed to the callback routines that the <i>CompletionRoutine</i> and <i>PostIrpRoutine </i>parameters point to. 

### -param CompletionRoutine [in, optional]

A pointer to a caller-supplied callback routine. If an opportunistic lock break is in progress, this routine is called when the break is completed. This parameter is optional and can be <b>NULL</b>. If it is <b>NULL</b>, the caller is put into a wait state until the opportunistic lock break is completed. 
This routine is declared as follows: 
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*POPLOCK_WAIT_COMPLETE_ROUTINE) (
      IN PVOID Context,
      IN PIRP Irp
      );</pre>
</td>
</tr>
</table></span></div>
This routine has the following parameters: 


### -param Context

A context information pointer that was passed in the <i>Context</i> parameter to <b>FsRtlCheckOplockEx</b>. 

### -param Irp

A pointer to the IRP for the I/O operation. 
</dd>
</dl>

### -param PostIrpRoutine [in, optional]

A pointer to a caller-supplied callback routine to be called if the I/O operation is posted to a work queue. This parameter is optional and can be <b>NULL</b>. 
This routine is declared as follows: 
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*POPLOCK_FS_PREPOST_IRP) (
      IN PVOID Context,
      IN PIRP Irp
      );</pre>
</td>
</tr>
</table></span></div>


### -param Context

A context information pointer that was passed in the <i>Context</i> parameter to <b>FsRtlCheckOplockEx</b>. 

### -param Irp

A pointer to the IRP for the I/O operation. 
</dd>
</dl>

## -returns
<b>FsRtlCheckOplockEx</b> returns STATUS_SUCCESS or an appropriate NTSTATUS code such as one of the following: 
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>The IRP was canceled. STATUS_CANCELLED is an error code. 
<dl>
<dt><b>STATUS_CANNOT_BREAK_OPLOCK</b></dt>
</dl>The opportunistic lock (oplock) break cannot be accomplished. The IRP is an IRP_MJ_CREATE request.  FILE_OPEN_REQUIRING_OPLOCK was specified in the create options parameter for the operation, and there is a granted oplock.
<dl>
<dt><b>STATUS_OPLOCK_BREAK_IN_PROGRESS</b></dt>
</dl>An opportunistic lock break is underway. The IRP is an IRP_MJ_CREATE request, and FILE_COMPLETE_IF_OPLOCKED was specified in the create options parameter for the operation. STATUS_OPLOCK_BREAK_IN_PROGRESS is a success code that is returned if OPLOCK_FLAG_COMPLETE_IF_OPLOCKED was set, and an opportunistic lock has been broken. 
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>An opportunistic lock break is underway, and control of the IRP was passed to the oplock package. If <i>CompletionRoutine</i> is <b>NULL</b>, <b>FsRtlCheckOplockEx</b> blocks while the opportunistic lock break is processed rather than return STATUS_PENDING. STATUS_PENDING is a success code. 

 

## -remarks
<b>FsRtlCheckOplockEx</b> synchronizes the IRP for an I/O operation with the current opportunistic lock state of a file according to the following conditions: 

If the I/O operation will cause the opportunistic lock to break, the opportunistic lock break is initiated. 

If the I/O operation cannot continue until the opportunistic lock break is complete and a completion routine in <i>CompletionRoutine</i> was specified, <b>FsRtlCheckOplockEx</b> returns STATUS_PENDING and calls the callback routine specified in <i>PostIrpRoutine</i>. When the opportunistic lock break has been acknowledged, the callback routine in <i>CompletionRoutine</i> is called.

•	If the I/O operation cannot continue until the opportunistic lock break is complete and <i>CompletionRoutine</i> was not specified, <b>FsRtlCheckOplockEx</b> will not return until the opportunistic lock break is acknowledged.

A <i>PostIrpRoutine</i> should be specified only if a <i>CompletionRoutine</i> has been specified.

If a file system or filter driver uses opportunistic locks, it must call <b>FsRtlCheckOplockEx</b> from any dispatch routines for I/O operations that can cause opportunistic lock breaks. This rule applies to the following types of I/O operations, because these operations can cause opportunistic lock breaks: 

IRP_MJ_CLEANUP

IRP_MJ_CREATE

IRP_MJ_FILE_SYSTEM_CONTROL

IRP_MJ_FLUSH_BUFFERS

IRP_MJ_LOCK_CONTROL

IRP_MJ_READ

IRP_MJ_SET_INFORMATION

IRP_MJ_WRITE

For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="ifsk.fltcheckoplockex">FltCheckOplockEx</a> instead of <b>FsRtlCheckOplockEx</b>. 

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
The <b>FsRtlCheckOplockEx</b> routine is available starting with Windows Vista. 
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
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
<a href="ifsk.fltcheckoplockex">FltCheckOplockEx</a>
</dt>
<dt>
<a href="ifsk.fsctl_opbatch_ack_close_pending">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>
</dt>
<dt>
<a href="ifsk.fsctl_oplock_break_ack_no_2">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>
</dt>
<dt>
<a href="ifsk.fsctl_oplock_break_acknowledge">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>
</dt>
<dt>
<a href="ifsk.fsctl_oplock_break_notify">FSCTL_OPLOCK_BREAK_NOTIFY</a>
</dt>
<dt>
<a href="ifsk.fsctl_request_batch_oplock">FSCTL_REQUEST_BATCH_OPLOCK</a>
</dt>
<dt>
<a href="ifsk.fsctl_request_filter_oplock">FSCTL_REQUEST_FILTER_OPLOCK</a>
</dt>
<dt>
<a href="ifsk.fsctl_request_oplock_level_1">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>
</dt>
<dt>
<a href="ifsk.fsctl_request_oplock_level_2">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>
</dt>
<dt>
<a href="ifsk.fsrtlcurrentbatchoplock">FsRtlCurrentBatchOplock</a>
</dt>
<dt>
<a href="ifsk.fsrtlinitializeoplock">FsRtlInitializeOplock</a>
</dt>
<dt>
<a href="ifsk.fsrtloplockfsctrl">FsRtlOplockFsctrl</a>
</dt>
<dt>
<a href="ifsk.fsrtloplockisfastiopossible">FsRtlOplockIsFastIoPossible</a>
</dt>
<dt>
<a href="ifsk.fsrtluninitializeoplock">FsRtlUninitializeOplock</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlCheckOplockEx routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
