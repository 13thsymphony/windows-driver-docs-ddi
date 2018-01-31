---
UID : NF:wdm.MmAllocateMdlForIoSpace
title : MmAllocateMdlForIoSpace function
author : windows-driver-content
description : The MmAllocateMdlForIoSpace routine allocates an MDL and initializes this MDL to describe a set of physical address ranges in I/O address space.
old-location : kernel\mmallocatemdlforiospace.htm
old-project : kernel
ms.assetid : 198ECC2A-1AC0-44FA-8E5C-84F1C8BEE246
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : MmAllocateMdlForIoSpace routine [Kernel-Mode Driver Architecture], kernel.mmallocatemdlforiospace, MmAllocateMdlForIoSpace, wdm/MmAllocateMdlForIoSpace
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# MmAllocateMdlForIoSpace function
The <b>MmAllocateMdlForIoSpace</b> routine allocates an <a href="..\wdm\ns-wdm-_mdl.md">MDL</a> and initializes this MDL to describe a set of physical address ranges in I/O address space.

## Syntax

````
NTSTATUS MmAllocateMdlForIoSpace(
  _In_  PMM_PHYSICAL_ADDRESS_LIST PhysicalAddressList,
  _In_  SIZE_T                    NumberOfEntries,
  _Out_ PMDL                      *NewMdl
);
````

## Parameters

`PhysicalAddressList`

A pointer to an array of <a href="..\wdm\ns-wdm-_mm_physical_address_list.md">MM_PHYSICAL_ADDRESS_LIST</a> structures that describe the physical address ranges to include in the allocated MDL.

`NumberOfEntries`

The number of elements in the <b>MM_PHYSICAL_ADDRESS_LIST</b> array pointed to by <i>PhysicalAddressList</i>.

`NewMdl`

A pointer to a location to which the routine writes a pointer to the newly allocated MDL.


## Return Value

<b>MmAllocateMdlForIoSpace</b> returns STATUS_SUCCESS if it is successful. Possible error return values include the following status codes.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
A physical address is not aligned to a page boundary; or a physical address range is not a multiple of the page size; or a physical address range is used by the operating system for RAM and is not available for use as I/O space.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient system resources are available to perform the requested operation.

</td>
</tr>
</table> 

Do not assume that the preceding list of error return codes is exhaustive. The routine might return error codes that do not appear in the list.

## Remarks

This routine accepts, as an input parameter, an array of <b>MM_PHYSICAL_ADDRESS_LIST</b> structures that describe a set of physical address ranges in I/O address space, and allocates an MDL that describes these ranges. Consecutive physical address ranges in the array are not required to be contiguous.

The physical address ranges in the <i>PhysicalAddressList</i> array must satisfy the following conditions:
<ul>
<li>The base physical address for each range must be aligned to a PAGE_SIZE boundary in memory.</li>
<li>The size, in bytes, of each range must be an integer multiple of PAGE_SIZE.</li>
<li>All physical address ranges must be in memory that is available for use as I/O address space. They cannot be in memory space that is used by the operating system for RAM.</li>
<li>The total size of all the ranges must be less than 4 gigabytes. Specifically, the total size must not exceed 2³²-1 bytes.</li>
</ul>The caller is responsible for freeing the allocated MDL when it is no longer needed. To free the MDL, call the <a href="..\wdm\nf-wdm-iofreemdl.md">IoFreeMdl</a> routine. For more information about MDLs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.

The MDL that is created by <b>MmAllocateMdlForIoSpace</b> is not mapped to virtual memory, but can be supplied to a routine such as <a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a> to initiate a DMA transfer to or from the physical memory ranges described by the MDL. To map this MDL to a contiguous range of virtual addresses so that it can be accessed by the processor, call the <a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a> routine.

Only ranges of the physical address space that are not reserved by the operating system for use as memory are available to drivers for use as I/O address space. Drivers use I/O address space to access memory-mapped hardware resources such as device registers. When a driver starts, it might receive one or more physical address ranges as translated hardware resources. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554399">Mapping Bus-Relative Addresses to Virtual Addresses</a>.

In some processor architectures, such as the x86, devices can be either memory-mapped or mapped to port addresses in a special  I/O address space that is dedicated to devices and is separate from the memory address space. Drivers can use <b>MmAllocateMdlForIoSpace</b> to allocate MDLs only for memory-mapped devices.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h) |
| **Library** |  |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a>

<a href="..\wdm\ns-wdm-_mdl.md">MDL</a>

<a href="..\wdm\ns-wdm-_mm_physical_address_list.md">MM_PHYSICAL_ADDRESS_LIST</a>

<a href="..\wdm\nf-wdm-iofreemdl.md">IoFreeMdl</a>

<a href="..\wdm\nc-wdm-pmap_transfer_ex.md">MapTransferEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmAllocateMdlForIoSpace routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>