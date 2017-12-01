---
UID: NF.ntddk.ZwTerminateProcess
title: ZwTerminateProcess
author: windows-driver-content
description: The ZwTerminateProcess routine terminates a process and all of its threads.
old-location: kernel\zwterminateprocess.htm
old-project: kernel
ms.assetid: 3b5e6de3-f1f4-4d7f-8c97-56a20a453ca3
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: ZwTerminateProcess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwTerminateProcess,NtTerminateProcess
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.iface: 
---

# ZwTerminateProcess function



## -description
<p>The <b>ZwTerminateProcess</b> routine terminates a process and all of its threads.</p>


## -syntax

````
NTSTATUS ZwTerminateProcess(
  _In_opt_ HANDLE   ProcessHandle,
  _In_     NTSTATUS ExitStatus
);
````


## -parameters
<dl>

### -param <i>ProcessHandle</i> [in, optional]

<dd>
<p>A handle to the process object that represents the process to be terminated. </p>
</dd>

### -param <i>ExitStatus</i> [in]

<dd>
<p>An NTSTATUS value that the operating system uses as the final status for the process and each of its threads. </p>
</dd>
</dl>

## -returns
<p><b>ZwTerminateProcess</b> returns STATUS_SUCCESS if the operation succeeds. Additional return values include:</p><dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl><p>The specified handle is not a process handle.</p><dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl><p>The specified handle is not valid.</p><dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl><p>The driver cannot access the specified process object.</p><dl>
<dt><b>STATUS_PROCESS_IS_TERMINATING</b></dt>
</dl><p>The specified process is already terminating. </p>

<p> </p>

<p>If the caller specifies the current process in the <i>ProcessHandle</i> parameter, <b>ZwTerminateProcess</b> does not return.</p>

## -remarks
<p>To obtain a process handle that a driver can specify for the <i>ProcessHandle</i> parameter, the driver can call <a href="..\ntddk\nf-ntddk-zwopenprocess.md">ZwOpenProcess</a>. The handle must be a <a href="wdkgloss.k#wdkgloss.kernel_handle#wdkgloss.kernel_handle"><i>kernel handle</i></a>.</p>

<p>Drivers must not specify the current process if resources have not been freed from the kernel stack, because the operating system will not unwind the kernel stack for the calling thread.</p>

<p>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.</p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-zwopenprocess.md">ZwOpenProcess</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwTerminateProcess routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
