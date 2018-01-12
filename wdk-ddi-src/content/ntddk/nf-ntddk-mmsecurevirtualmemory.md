---
UID: NF:ntddk.MmSecureVirtualMemory
title: MmSecureVirtualMemory function
author: windows-driver-content
description: The MmSecureVirtualMemory routine secures a user-space memory address range so that it cannot be freed and its protection type cannot be made more restrictive.
old-location: kernel\mmsecurevirtualmemory.htm
old-project: kernel
ms.assetid: e5c2d5d5-550e-42e5-b86a-f17e361925dc
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: MmSecureVirtualMemory
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
req.alt-api: MmSecureVirtualMemory
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <=APC_LEVEL
req.typenames: *PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT
---

# MmSecureVirtualMemory function



## -description
The <b>MmSecureVirtualMemory</b> routine secures a user-space memory address range so that it cannot be freed and its protection type cannot be made more restrictive.



## -syntax

````
HANDLE MmSecureVirtualMemory(
  _In_ PVOID  Address,
  _In_ SIZE_T Size,
  _In_ ULONG  ProbeMode
);
````


## -parameters

### -param Address [in]

The beginning of the user virtual address range to secure.


### -param Size [in]

The size, in bytes, of the virtual address range to secure.


### -param ProbeMode [in]

The most restrictive protection type that is allowed. Use PAGE_READWRITE to specify that address range must remain both readable and writable, or use PAGE_READONLY to specify the address range must only remain readable.


## -returns
On success, <b>MmSecureVirtualMemory</b> returns an opaque pointer value that the driver passes to the <a href="..\ntddk\nf-ntddk-mmunsecurevirtualmemory.md">MmUnsecureVirtualMemory</a> routine to unsecure the memory address range. If the routine is unable to secure the memory address range, it returns <b>NULL</b>.


## -remarks
<b>MmSecureVirtualMemory</b> can be used to avoid certain race conditions on user-mode buffers. For example, if a driver checks to see if the buffer is writable, but then the originating user-mode process changes the buffer to be read-only before the driver can write to the buffer, then a race condition can result. A driver that uses <b>MmSecureVirtualMemory</b> is guaranteed that if the requested protection mode is available, it cannot be changed until the driver calls <a href="..\ntddk\nf-ntddk-mmunsecurevirtualmemory.md">MmUnsecureVirtualMemory</a>. The routine also protects against the originating user-mode process freeing the buffer. Here are a few guidelines about calling those routines:<ul>
<li>
If a driver calls <b>MmSecureVirtualMemory</b> and does not call <a href="..\ntddk\nf-ntddk-mmunsecurevirtualmemory.md">MmUnsecureVirtualMemory</a>, the memory is automatically unsecured when the process terminates.

</li>
<li>
If the driver calls <a href="..\ntddk\nf-ntddk-mmunsecurevirtualmemory.md">MmUnsecureVirtualMemory</a>, it must call it in the context of the process in which the memory was originally secured, and before that process terminates.

</li>
<li>
Typically drivers need to reference the process when they secure the memory, then later call <a href="..\ntifs\nf-ntifs-kestackattachprocess.md">KeStackAttachProcess</a> to switch to the context of that process before calling <a href="..\ntddk\nf-ntddk-mmunsecurevirtualmemory.md">MmUnsecureVirtualMemory</a>.

</li>
<li>
To detect process termination drivers can use <a href="..\ntddk\nf-ntddk-pssetcreateprocessnotifyroutine.md">PsSetCreateProcessNotifyRoutine</a>. Alternatively, the process can submit an IRP with a cancel routine that is invoked by the I/O manager when the process is exiting. In the cancel routine the driver can attach to the process and call <a href="..\ntddk\nf-ntddk-mmunsecurevirtualmemory.md">MmUnsecureVirtualMemory</a>.

</li>
</ul>


If a driver calls <b>MmSecureVirtualMemory</b> and does not call <a href="..\ntddk\nf-ntddk-mmunsecurevirtualmemory.md">MmUnsecureVirtualMemory</a>, the memory is automatically unsecured when the process terminates.

If the driver calls <a href="..\ntddk\nf-ntddk-mmunsecurevirtualmemory.md">MmUnsecureVirtualMemory</a>, it must call it in the context of the process in which the memory was originally secured, and before that process terminates.

Typically drivers need to reference the process when they secure the memory, then later call <a href="..\ntifs\nf-ntifs-kestackattachprocess.md">KeStackAttachProcess</a> to switch to the context of that process before calling <a href="..\ntddk\nf-ntddk-mmunsecurevirtualmemory.md">MmUnsecureVirtualMemory</a>.

To detect process termination drivers can use <a href="..\ntddk\nf-ntddk-pssetcreateprocessnotifyroutine.md">PsSetCreateProcessNotifyRoutine</a>. Alternatively, the process can submit an IRP with a cancel routine that is invoked by the I/O manager when the process is exiting. In the cancel routine the driver can attach to the process and call <a href="..\ntddk\nf-ntddk-mmunsecurevirtualmemory.md">MmUnsecureVirtualMemory</a>.

While calling <b>MmSecureVirtualMemory</b> on an address range prevents the address range from being freed or from having its protection changed, it does not protect against other types of raised exceptions. (For example, it does not protect against an exception raised when the system finds a bad disk block in the page file.)  Therefore, drivers must still wrap any memory accesses in a <b>try/except</b> block. Therefore, we recommend that drivers do not use this function. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546823">Handling Exceptions</a>. 


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
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
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
&lt;=APC_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/075f5710-b2bf-4546-9648-661a3c8521f8">IrqlMmApcLte</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-mmunsecurevirtualmemory.md">MmUnsecureVirtualMemory</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmSecureVirtualMemory routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

