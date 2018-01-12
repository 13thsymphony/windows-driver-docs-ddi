---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlOplockFsctrl~r2
title: FsRtlOplockFsctrl function
author: windows-driver-content
description: FsRtlOplockFsctrl performs various opportunistic lock (oplock) operations on behalf of a file system or filter driver.
old-location: ifsk\fsrtloplockfsctrl.htm
old-project: ifsk
ms.assetid: e456189e-9513-47a7-b5b0-384b531dbda9
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlOplockFsctrl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlOplockFsctrl
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
req.typenames: TOKEN_TYPE
---

# FsRtlOplockFsctrl function



## -description
<b>FsRtlOplockFsctrl</b> performs various opportunistic lock (oplock) operations on behalf of a file system or filter driver. 



## -syntax

````
NTSTATUS FsRtlOplockFsctrl(
  _In_ POPLOCK Oplock,
  _In_ PIRP    Irp,
  _In_ ULONG   OpenCount
);
````


## -parameters

### -param Oplock [in]

Opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>. 


### -param Irp [in]

Pointer to the IRP for the I/O operation. This parameter is required and cannot be <b>NULL</b>. 


### -param OpenCount [in]

Number of user handles for the file, if an exclusive opportunistic lock is being requested. Setting a nonzero value for a level 2, R, or RH oplock request indicates that there are byte-range locks on the file. For information about oplock types, see <a href="https://msdn.microsoft.com/e9a45ae0-0ec8-4d6c-8486-ae88bdaa1f8c">Oplock Semantics Overview</a>. 


## -returns
<b>FsRtlOplockFsctrl</b> returns one of the following NTSTATUS values: 
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>For an IRP_MJ_CREATE request, STATUS_SUCCESS indicates that the requested filter opportunistic lock was granted. For a FSCTL operation, the meaning of STATUS_SUCCESS depends on the FSCTL code. For more information, see the reference pages for the FSCTL codes listed in the following Remarks section. 
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>The I/O operation was canceled. STATUS_CANCELLED is an error code. 
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The FSCTL code for the I/O operation was not one of the valid values listed in the following Remarks section. STATUS_INVALID_PARAMETER is an error code. 
<dl>
<dt><b>STATUS_OPLOCK_NOT_GRANTED</b></dt>
</dl>The opportunistic lock could not be granted. STATUS_OPLOCK_NOT_GRANTED is an error code. 
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>Used only for FSCTL operations. The meaning of STATUS_PENDING depends on the FSCTL code. For more information, see the reference pages for the FSCTL codes listed in the following Remarks section. STATUS_PENDING is a success code. 
<dl>
<dt><b>STATUS_CANNOT_BREAK_OPLOCK </b></dt>
</dl>A new opportunistic lock (oplock) could not be granted. The IRP is an IRP_MJ_CREATE request and FILE_OPEN_REQUIRING_OPLOCK was specified in the create options parameter for the operation. STATUS_CANNOT_BREAK_OPLOCK is a success code. 

 


## -remarks
File systems and filter drivers call <b>FsRtlOplockFsctrl</b> to perform various opportunistic lock operations for a create or file system control I/O operation. The IRP pointed to by the <i>Irp</i> parameter must be a valid IRP for an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550751">IRP_MJ_FILE_SYSTEM_CONTROL</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a> operation. 

If the IRP is an IRP_MJ_FILE_SYSTEM_CONTROL request, <b>FsRtlOplockFsctrl</b> can be used with the following FSCTL codes. The FSCTL code is set in IrpSp-&gt;Parameters.FileSystemControl.FsControlCode. For more information about file system control parameters, see the reference entry for <a href="https://msdn.microsoft.com/library/windows/hardware/ff550751">IRP_MJ_FILE_SYSTEM_CONTROL</a>. 


<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>


For detailed information about these FSCTLs and about opportunistic locks in general, see the Microsoft Windows SDK documentation. 

If the IRP is an IRP_MJ_CREATE request, <b>FsRtlOplockFsctrl</b> can be used to request a pending filter opportunistic lock if all of the following conditions are true: 

The value of the <i>OpenCount</i> parameter must be 1. 

The value of the <i>DesiredAccess</i> parameter for the IRP_MJ_CREATE request must be FILE_READ_ATTRIBUTES. 

The value of the <i>ShareAccess</i> parameter for the IRP_MJ_CREATE request must be FILE_SHARE_READ | FILE_SHARE_WRITE | FILE_SHARE_DELETE. 

If the request for a pending filter opportunistic lock is granted, <b>FsRtlOplockFsctrl</b> returns STATUS_SUCCESS. For more information about create parameters, see the reference entry for <a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>. 

Minifilters should call <a href="..\fltkernel\nf-fltkernel-fltoplockfsctrl.md">FltOplockFsctrl</a> instead of <b>FsRtlOplockFsctrl</b>. 


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
<a href="..\fltkernel\nf-fltkernel-fltoplockfsctrl.md">FltOplockFsctrl</a>
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
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcurrentbatchoplock.md">FsRtlCurrentBatchOplock</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-fsrtloplockisfastiopossible.md">FsRtlOplockIsFastIoPossible</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock.md">FsRtlUninitializeOplock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548630">IRP_MJ_CREATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550751">IRP_MJ_FILE_SYSTEM_CONTROL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlOplockFsctrl function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

