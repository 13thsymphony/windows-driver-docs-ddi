---
UID: NF.ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlOplockFsctrlEx~r3
title: FsRtlOplockFsctrlEx function
author: windows-driver-content
description: The FsRtlOplockFsctrlEx routine performs various opportunistic lock (oplock) operations on behalf of a file system or filter driver.
old-location: ifsk\fsrtloplockfsctrlex.htm
old-project: ifsk
ms.assetid: f1bac8c1-a313-40b9-96fc-9eaf426bf238
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FsRtlOplockFsctrlEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlOplockFsctrlEx routine is available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlOplockFsctrlEx
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

# FsRtlOplockFsctrlEx function



## -description
The <b>FsRtlOplockFsctrlEx</b> routine performs various opportunistic lock (oplock) operations on behalf of a file system or filter driver. 



## -syntax

````
NTSTATUS FsRtlOplockFsctrlEx(
  _In_ POPLOCK Oplock,
  _In_ PIRP    Irp,
  _In_ ULONG   OpenCount,
  _In_ ULONG   Flags
);
````


## -parameters

### -param Oplock [in]

An opaque oplock pointer for the file. This pointer must have been initialized by a previous call to <a href="ifsk.fsrtlinitializeoplock">FsRtlInitializeOplock</a>. 


### -param Irp [in]

A pointer to the IRP for the I/O operation. This parameter is required and cannot be <b>NULL</b>. 


### -param OpenCount [in]

Number of user handles for the file, if an exclusive oplock is being requested. Setting a nonzero value for a level 2, R, or RH oplock request indicates that there are byte-range locks on the file. For information about oplock types, see <a href="https://msdn.microsoft.com/e9a45ae0-0ec8-4d6c-8486-ae88bdaa1f8c">Oplock Semantics Overview</a>. 


### -param Flags [in]

A bitmask for the associated oplock operations. A file system or filter driver sets bits to specify the behavior of <b>FsRtlOplockFsctrlEx</b>. The <i>Flags</i> parameter has the following options:




### -param OPLOCK_FSCTRL_FLAG_ALL_KEYS_MATCH (0x00000001)

Specifies that the file system verified that all oplock keys on any currently open handles match. By specifying this flag, you allow the oplock package to grant an oplock of level RW or RWH when more than one open handle to the file exists. For more information about oplock types, see the Oplock Semantics <a href="https://msdn.microsoft.com/e9a45ae0-0ec8-4d6c-8486-ae88bdaa1f8c">Overview</a> page. 

</dd>
</dl>

## -returns
<b>FsRtlOplockFsctrlEx</b> returns one of the following NTSTATUS values: 
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>For an IRP_MJ_CREATE request, STATUS_SUCCESS indicates that the requested filter opportunistic lock (oplock) was granted. For a FSCTL operation, the meaning of STATUS_SUCCESS depends on the FSCTL code. For more information, see the reference pages for the FSCTL codes that are listed in the following Remarks section. 
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>The I/O operation was canceled. STATUS_CANCELLED is an error code. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The FSCTL code for the I/O operation was not one of the valid values listed in the following Remarks section. STATUS_INVALID_PARAMETER is an error code. 
<dl>
<dt><b>STATUS_OPLOCK_NOT_GRANTED</b></dt>
</dl>The oplock could not be granted. STATUS_OPLOCK_NOT_GRANTED is an error code. 
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>Used only for FSCTL operations. The meaning of STATUS_PENDING depends on the FSCTL code. For more information, see the reference pages for the FSCTL codes that are listed in the following Remarks section. STATUS_PENDING is a success code. 

 


## -remarks
File systems and filter drivers call <b>FsRtlOplockFsctrlEx</b> to perform various opportunistic lock operations for a create operation or file system control I/O operation. The IRP pointed to by the <i>Irp</i> parameter must be a valid IRP for an <a href="ifsk.irp_mj_file_system_control">IRP_MJ_FILE_SYSTEM_CONTROL</a> or <a href="ifsk.irp_mj_create">IRP_MJ_CREATE</a> operation. 

If the IRP is an IRP_MJ_FILE_SYSTEM_CONTROL request, <b>FsRtlOplockFsctrlEx</b> can be used with the following FSCTL codes. The FSCTL code is set in IrpSp-&gt;Parameters.FileSystemControl.FsControlCode. For more information about file system control parameters, see the reference entry for <a href="ifsk.irp_mj_file_system_control">IRP_MJ_FILE_SYSTEM_CONTROL</a>. 


<a href="ifsk.fsctl_opbatch_ack_close_pending">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="ifsk.fsctl_oplock_break_ack_no_2">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="ifsk.fsctl_oplock_break_acknowledge">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="ifsk.fsctl_oplock_break_notify">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="ifsk.fsctl_request_batch_oplock">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="ifsk.fsctl_request_filter_oplock">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="ifsk.fsctl_request_oplock_level_1">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="ifsk.fsctl_request_oplock_level_2">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="ifsk.fsctl_request_oplock">FSCTL_REQUEST_OPLOCK</a>


For more information information about these FSCTLs and about opportunistic locks in general, see the Microsoft Windows SDK documentation. 

If the IRP is an IRP_MJ_CREATE request, <b>FsRtlOplockFsctrlEx</b> can be used to request a pending filter opportunistic lock (oplock) if all of the following conditions are true: 

The value of the <i>OpenCount</i> parameter must be 1. 

The value of the <i>DesiredAccess</i> parameter for the IRP_MJ_CREATE request must be FILE_READ_ATTRIBUTES. 

The value of the <i>ShareAccess</i> parameter for the IRP_MJ_CREATE request must be FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE. 

If the request for a pending filter oplock is granted, <b>FsRtlOplockFsctrlEx</b> returns STATUS_SUCCESS. For more information about create parameters, see <a href="ifsk.irp_mj_create">IRP_MJ_CREATE</a>. 

Minifilters should call <a href="ifsk.fltoplockfsctrlex">FltOplockFsctrlEx</a> instead of <b>FsRtlOplockFsctrlEx</b>. 


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
The FsRtlOplockFsctrlEx routine is available starting with Windows 7. 

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
<a href="ifsk.fltoplockfsctrlex">FltOplockFsctrlEx</a>
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
<a href="ifsk.fsctl_request_oplock">FSCTL_REQUEST_OPLOCK</a>
</dt>
<dt>
<a href="ifsk.fsctl_request_oplock_level_1">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>
</dt>
<dt>
<a href="ifsk.fsctl_request_oplock_level_2">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>
</dt>
<dt>
<a href="ifsk.fsrtlinitializeoplock">FsRtlInitializeOplock</a>
</dt>
<dt>
<a href="ifsk.irp_mj_create">IRP_MJ_CREATE</a>
</dt>
<dt>
<a href="ifsk.irp_mj_file_system_control">IRP_MJ_FILE_SYSTEM_CONTROL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlOplockFsctrlEx routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

