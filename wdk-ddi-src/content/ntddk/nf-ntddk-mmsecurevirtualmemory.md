---
UID: NF:ntddk.MmSecureVirtualMemory
title: MmSecureVirtualMemory function
author: windows-driver-content
description: The MmSecureVirtualMemory routine secures a user-space memory address range so that it cannot be freed and its protection type cannot be made more restrictive.
old-location: kernel\mmsecurevirtualmemory.htm
old-project: kernel
ms.assetid: e5c2d5d5-550e-42e5-b86a-f17e361925dc
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: MmSecureVirtualMemory, MmSecureVirtualMemory routine [Kernel-Mode Driver Architecture], k106_d85881bb-59a3-4494-afaa-55c49b71b64b.xml, kernel.mmsecurevirtualmemory, ntddk/MmSecureVirtualMemory
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
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmSecureVirtualMemory
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# MmSecureVirtualMemory function
The <b>MmSecureVirtualMemory</b> routine secures a user-space memory address range so that it cannot be freed and its protection type cannot be made more restrictive.

## Syntax

````
HANDLE MmSecureVirtualMemory(
  _In_ PVOID  Address,
  _In_ SIZE_T Size,
  _In_ ULONG  ProbeMode
);
````

## Parameters

`Address`

The beginning of the user virtual address range to secure.

`Size`

The size, in bytes, of the virtual address range to secure.

`ProbeMode`

The most restrictive protection type that is allowed. Use PAGE_READWRITE to specify that address range must remain both readable and writable, or use PAGE_READONLY to specify the address range must only remain readable.


## Return Value

On success, <b>MmSecureVirtualMemory</b> returns an opaque pointer value that the driver passes to the <a href="..\ntddk\nf-ntddk-mmunsecurevirtualmemory.md">MmUnsecureVirtualMemory</a> routine to unsecure the memory address range. If the routine is unable to secure the memory address range, it returns <b>NULL</b>.

## Remarks

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


While calling <b>MmSecureVirtualMemory</b> on an address range prevents the address range from being freed or from having its protection changed, it does not protect against other types of raised exceptions. (For example, it does not protect against an exception raised when the system finds a bad disk block in the page file.)  Therefore, drivers must still wrap any memory accesses in a <b>try/except</b> block. Therefore, we recommend that drivers do not use this function. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546823">Handling Exceptions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<=APC_LEVEL" |
| **DDI compliance rules** | IrqlMmApcLte, HwStorPortProhibitedDDIs |

## See Also

<a href="..\ntddk\nf-ntddk-mmunsecurevirtualmemory.md">MmUnsecureVirtualMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmSecureVirtualMemory routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>