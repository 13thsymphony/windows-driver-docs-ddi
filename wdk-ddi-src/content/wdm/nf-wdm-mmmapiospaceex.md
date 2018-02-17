---
UID: NF:wdm.MmMapIoSpaceEx
title: MmMapIoSpaceEx function
author: windows-driver-content
description: The MmMapIoSpaceEx routine maps the given physical address range to non-paged system space using the specified page protection.
old-location: kernel\mmmapiospaceex.htm
old-project: kernel
ms.assetid: 0A8216B2-822D-4157-876E-AA0A1A9D6D3F
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.mmmapiospaceex, MmMapIoSpace, MmMapIoSpaceEx, MmMapIoSpace routine [Kernel-Mode Driver Architecture], wdm/MmMapIoSpace
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 10.
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmMapIoSpace
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# MmMapIoSpaceEx function
The <b>MmMapIoSpaceEx</b> routine maps the given physical address range to non-paged system space using the specified page protection.

## Syntax

````
PVOID MmMapIoSpace(
  _In_ PHYSICAL_ADDRESS PhysicalAddress,
  _In_ SIZE_T           NumberOfBytes,
  _In_ ULONG            Protect
);
````

## Parameters

`PhysicalAddress`

Specifies the starting physical address of the I/O range to be mapped.

`NumberOfBytes`

Specifies a value greater than zero, indicating the number of bytes to be mapped.

`Protect`

Flag bits that specify the protection to use for the mapped range. The caller must set one of the following flag bits in the <i>Protect</i> parameter.

<table>
<tr>
<th>Flag bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>PAGE_READONLY</td>
<td>The mapped range can only be read, not written. </td>
</tr>
<tr>
<td>PAGE_READWRITE</td>
<td>The mapped range can be read or written. </td>
</tr>
<tr>
<td>PAGE_EXECUTE</td>
<td>The mapped range can be executed, but not read or written.</td>
</tr>
<tr>
<td>PAGE_EXECUTE_READ</td>
<td>The mapped range can be executed or read, but not written.</td>
</tr>
<tr>
<td>PAGE_EXECUTE_READWRITE</td>
<td>The mapped range can be executed, read, or written. </td>
</tr>
</table>
 

In addition, the caller can set one (but not both) of the following optional flag bits in the <i>Protect</i> parameter.

<table>
<tr>
<th>Flag bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>PAGE_NOCACHE</td>
<td>Specifies non-cached memory.</td>
</tr>
<tr>
<td>PAGE_WRITECOMBINE</td>
<td>Specifies write-combined memory (the memory should not be cached by the processor, but writes to the memory can be combined by the processor).</td>
</tr>
</table>


## Return Value

<b>MmMapIoSpaceEx</b> returns the base virtual address that maps the base physical address for the range. If space for mapping the range is insufficient, it returns <b>NULL</b>.

## Remarks

A driver must call this routine during device start-up if it receives translated resources of type <b>CmResourceTypeMemory</b> in a <a href="..\wdm\ns-wdm-_cm_partial_resource_descriptor.md">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure. <b>MmMapIoSpaceEx</b> maps the physical address returned in the resource list to a logical address through which the driver can access device registers.

For example, drivers of PIO devices that allocate long-term I/O buffers can call this routine to make such buffers accessible or to make device memory accessible.

For more information about using this routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554399">Mapping Bus-Relative Addresses to Virtual Addresses</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 10.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\wdm\nf-wdm-mmunmapiospace.md">MmUnmapIoSpace</a>



<a href="..\ntddk\nf-ntddk-mmallocatenoncachedmemory.md">MmAllocateNonCachedMemory</a>



<a href="..\wdm\nf-wdm-mmallocatecontiguousmemory.md">MmAllocateContiguousMemory</a>



<a href="..\wdm\nf-wdm-mmmaplockedpages.md">MmMapLockedPages</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmMapIoSpaceEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>