---
UID: NF.fltkernel.FltOplockFsctrl
title: FltOplockFsctrl
author: windows-driver-content
description: The FltOplockFsctrl routine performs various opportunistic lock (oplock) operations on behalf of a minifilter driver.
old-location: ifsk\fltoplockfsctrl.htm
old-project: ifsk
ms.assetid: 50fba819-7a6c-472d-a8e3-5790bc6ec249
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltOplockFsctrl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltOplockFsctrl
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
req.iface: 
---

# FltOplockFsctrl function



## -description
<p>The <b>FltOplockFsctrl</b> routine performs various opportunistic lock (oplock) operations on behalf of a minifilter driver. </p>


## -syntax

````
FLT_PREOP_CALLBACK_STATUS FltOplockFsctrl(
  _In_ POPLOCK            Oplock,
  _In_ PFLT_CALLBACK_DATA CallbackData,
  _In_ ULONG              OpenCount
);
````


## -parameters
<dl>

### -param Oplock [in]

<dd>
<p>Opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>. </p>
</dd>

### -param CallbackData [in]

<dd>
<p>Pointer to the callback data structure for the I/O operation (<a href="..\fltkernel\ns-fltkernel--flt-callback-data.md">FLT_CALLBACK_DATA</a>). This parameter is required and cannot be <b>NULL</b>. </p>
</dd>

### -param OpenCount [in]

<dd>
<p>Number of user handles for the file, if an exclusive oplock is being requested. Setting a nonzero value for a level 2, R, or RH oplock request indicates that there are byte-range locks on the file. For information about oplock types, see <a href="https://msdn.microsoft.com/e9a45ae0-0ec8-4d6c-8486-ae88bdaa1f8c">Oplock Semantics Overview</a>. </p>
</dd>
</dl>

## -returns
<p><b>FltOplockFsctrl</b> returns FLT_PREOP_PENDING for some FSCTL operations. For more information, see the reference pages for the FSCTL codes listed in the following Remarks section. Otherwise, <b>FltOplockFsctrl</b> returns FLT_PREOP_COMPLETE. </p>

## -remarks
<p>A minifilter driver calls <b>FltOplockFsctrl</b> to perform various opportunistic lock operations for a create or file system control I/O operation. The FLT_CALLBACK_DATA structure pointed to by the <i>CallbackData</i> parameter must represent an IRP-based <a href="ifsk.irp_mj_file_system_control">IRP_MJ_FILE_SYSTEM_CONTROL</a> or <a href="ifsk.irp_mj_create">IRP_MJ_CREATE</a> operation. </p>

<p>If the operation is an IRP_MJ_FILE_SYSTEM_CONTROL operation, <b>FltOplockFsctrl</b> can be used with the following FSCTL codes: </p>

<p>
<a href="ifsk.fsctl_opbatch_ack_close_pending">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>
</p>

<p>
<a href="ifsk.fsctl_oplock_break_ack_no_2">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>
</p>

<p>
<a href="ifsk.fsctl_oplock_break_acknowledge">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>
</p>

<p>
<a href="ifsk.fsctl_oplock_break_notify">FSCTL_OPLOCK_BREAK_NOTIFY</a>
</p>

<p>
<a href="ifsk.fsctl_request_batch_oplock">FSCTL_REQUEST_BATCH_OPLOCK</a>
</p>

<p>
<a href="ifsk.fsctl_request_filter_oplock">FSCTL_REQUEST_FILTER_OPLOCK</a>
</p>

<p>
<a href="ifsk.fsctl_request_oplock_level_1">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>
</p>

<p>
<a href="ifsk.fsctl_request_oplock_level_2">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>
</p>

<p>The FSCTL code is set in the <b>FsControlCode</b> member of the <a href="..\fltkernel\ns-fltkernel--flt-parameters.md">FLT_PARAMETERS</a> structure for the operation. For more information about <b>FsControlCode</b> and other IRP_MJ_FILE_SYSTEM_CONTROL parameters, see <a href="ifsk.flt_parameters_for_irp_mj_file_system_control">FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL</a>. </p>

<p>For more information about opportunistic locks, see the Microsoft Windows SDK documentation. </p>

<p>If the operation is an <a href="ifsk.irp_mj_create">IRP_MJ_CREATE</a> request, <b>FltOplockFsctrl</b> can be used to request a pending filter opportunistic lock if all of the following conditions are true: </p>

<p>The value of the <i>OpenCount</i> parameter is 1. </p>

<p>The value of the <i>DesiredAccess</i> parameter for the IRP_MJ_CREATE request is FILE_READ_ATTRIBUTES. This parameter is set in the <b>SecurityContext</b> member of the FLT_PARAMETERS structure for the operation. For more information, see <a href="ifsk.flt_parameters_for_irp_mj_create">FLT_PARAMETERS for IRP_MJ_CREATE</a>. </p>

<p>The value of the <i>ShareAccess</i> parameter for the IRP_MJ_CREATE operation is FILE_SHARE_READ, FILE_SHARE_WRITE, or FILE_SHARE_DELETE. This parameter is set in the <b>ShareAccess</b> member of the FLT_PARAMETERS structure for the operation. For more information, see <a href="ifsk.flt_parameters_for_irp_mj_create">FLT_PARAMETERS for IRP_MJ_CREATE</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Fltkernel.h (include Fltkernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>FltMgr.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>Fltmgr.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel--flt-callback-data.md">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="ifsk.flt_parameters_for_irp_mj_create">FLT_PARAMETERS for IRP_MJ_CREATE</a>
</dt>
<dt>
<a href="ifsk.flt_parameters_for_irp_mj_file_system_control">FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcheckoplock.md">FltCheckOplock</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcurrentbatchoplock.md">FltCurrentBatchOplock</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltoplockisfastiopossible.md">FltOplockIsFastIoPossible</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltuninitializeoplock.md">FltUninitializeOplock</a>
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
<a href="ifsk.fsrtloplockfsctrl">FsRtlOplockFsctrl</a>
</dt>
<dt>
<a href="ifsk.irp_mj_create">IRP_MJ_CREATE</a>
</dt>
<dt>
<a href="ifsk.irp_mj_file_system_control">IRP_MJ_FILE_SYSTEM_CONTROL</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltOplockFsctrl routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
