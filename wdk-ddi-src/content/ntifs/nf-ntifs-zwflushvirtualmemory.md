---
UID: NF:ntifs.ZwFlushVirtualMemory
title: ZwFlushVirtualMemory function
author: windows-driver-content
description: The ZwFlushVirtualMemory routine flushes a range of virtual addresses within the virtual address space of a specified process which map to a data file back out to the data file if they have been modified.
old-location: kernel\zwflushvirtualmemory.htm
old-project: kernel
ms.assetid: 86e04896-2921-4f77-9bee-283ceb9a66bc
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ZwFlushVirtualMemory routine [Kernel-Mode Driver Architecture], ntifs/NtFlushVirtualMemory, ZwFlushVirtualMemory, k111_536d2679-dc41-490f-be7b-171e0208a1fd.xml, kernel.zwflushvirtualmemory, NtFlushVirtualMemory, ntifs/ZwFlushVirtualMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwFlushVirtualMemory
-	NtFlushVirtualMemory
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# ZwFlushVirtualMemory function
The <b>ZwFlushVirtualMemory</b> routine flushes a range of virtual addresses within the virtual address space of a specified process which map to a data file back out to the data file if they have been modified.

## Syntax

````
NTSTATUS ZwFlushVirtualMemory(
  _In_    HANDLE           ProcessHandle,
  _Inout_ PVOID            *BaseAddress,
  _Inout_ PSIZE_T          RegionSize,
  _Out_   PIO_STATUS_BLOCK IoStatus
);
````

## Parameters

`ProcessHandle`

An open handle for the process in whose context the pages to be flushed reside. Use the <b>NtCurrentProcess</b> macro, defined in Ntddk.h, to specify the current process.

`BaseAddress`

A pointer to the base address of the virtual address range.

On entry, this parameter specifies a pointer to the initial value of the base address of the region of pages to flush.

On return, this parameter provides a pointer to a variable that will receive the base address of the flushed region.

`RegionSize`

The size, in bytes, of the virtual address range.

On entry, this parameter specifies a pointer to the initial value of the size in bytes of the region of pages to flush to disk. This argument is rounded up to the next host-page-size boundary by the <b>ZwFlushVirtualMemory</b>. If this value is specified as zero, the mapped range from the base address to the end of the range is flushed.

On return, this parameter specifies a pointer to a variable that will receive the actual size in bytes of the flushed region of pages.

`IoStatus`

A pointer to an <a href="..\wdm\ns-wdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure. This structure is where the value of the I/O status for the last attempted I/O operation is stored on output.


## Return Value

<b>ZwFlushVirtualMemory</b> returns either STATUS_SUCCESS or an error status code. Possible error status codes include the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>ProcessHandle</i> parameter was not a valid process handle. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Additional resources required by this function were not available. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_2</b></dt>
</dl>
</td>
<td width="60%">
The <i>BaseAddress</i> specified was an invalid address within the virtual address space or the <i>RegionSize</i> was invalid. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>ProcessHandle</i> parameter was not a valid process handle. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_MAPPED_VIEW</b></dt>
</dl>
</td>
<td width="60%">
No virtual address space descriptor could be located for the supplied <i>BaseAddress</i>. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PROCESS_IS_TERMINATING</b></dt>
</dl>
</td>
<td width="60%">
The process and the associated virtual address space was deleted. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FILE_LOCK_CONFLICT</b></dt>
</dl>
</td>
<td width="60%">
The file system encountered a locking conflict. 

</td>
</tr>
</table>

## Remarks

This routine accepts, as input parameters, a range of addresses in virtual memory that map a data file. If any memory in this range has been modified since the file was copied to memory, the routine flushes this memory back to the data file.

For more information about memory management support for kernel-mode drivers, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554389">Memory Management for Windows Drivers</a>. 

<div class="alert"><b>Note</b>  If the call to the <b>ZwFlushVirtualMemory</b> function occurs in user mode, you should use the name "<b>NtFlushVirtualMemory</b> " instead of "<b>ZwFlushVirtualMemory</b>".</div>
<div> </div>
For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows XP. Available starting with Windows XP. |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ntifs\nf-ntifs-zwallocatevirtualmemory.md">ZwAllocateVirtualMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwFlushVirtualMemory routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>