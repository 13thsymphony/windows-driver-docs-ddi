---
UID : NF:ntifs.ZwSetInformationVirtualMemory
title : ZwSetInformationVirtualMemory function
author : windows-driver-content
description : The ZwSetInformationVirtualMemory routine performs an operation on a specified list of address ranges in the user address space of a process.
old-location : kernel\zwsetinformationvirtualmemory.htm
old-project : kernel
ms.assetid : 1D53D6C6-7546-439F-818C-85E65901B5DC
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ZwSetInformationVirtualMemory
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntddk.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 10, version 1511.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : ZwSetInformationVirtualMemory
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL
req.typenames : TOKEN_TYPE
---


# ZwSetInformationVirtualMemory function
The <b>ZwSetInformationVirtualMemory</b> routine performs an operation on a specified list of address ranges in the user address space of a process.

## Syntax

````
NTSTATUS ZwSetInformationVirtualMemory(
  _In_ HANDLE                                ProcessHandle,
  _In_ VIRTUAL_MEMORY_INFORMATION_CLASS      VmInformationClass,
  _In_ ULONG_PTR                             NumberOfEntries,
  _In_ (NumberOfEntries) PMEMORY_RANGE_ENTRY VirtualAddresses,
  _In_ (VmInformationLength) PVOID           VmInformation,
  _In_ ULONG                                 VmInformationLength
);
````

## Parameters

`ProcessHandle`

Specifies an open handle for the process in the context of which the operation is to be performed. This handle cannot be invalid. Use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556482">NtCurrentProcess</a> macro, defined in Ntddk.h, to specify the current process.

`VmInformationClass`

Specifies the type of operation to perform. Set to  <b>VmPrefetchInformation</b> defined in the <b>VIRTUAL_MEMORY_INFORMATION_CLASS</b> enumeration, see ntddk.h.

`NumberOfEntries`

Number of entries in the array pointed to by the <i>VirtualAddresses</i> parameter. This parameter cannot be 0.

`VirtualAddresses`

Pointer to an array of MEMORY_RANGE_ENTRY structures in which each entry specifies a virtual address range to be processed. The virtual address ranges may cover any part of the process address space accessible by the target process.

`VmInformation`

A pointer to a buffer that contains memory information.
                    The format and content of the buffer depend on the
                    specified information class.


If <i>VmInformationClass</i> is  <b>VmPrefetchInformation</b>, this parameter cannot be this parameter cannot be NULL and must point to a ULONG variable that is set to 0.

`VmInformationLength`

The size of the buffer pointed to by  <i>VmInformation</i>. 

If <i>VmInformationClass</i> is <b>VmPrefetchInformation</b>, this must be <code>sizeof (ULONG)</code>.


## Return Value

<b>ZwSetInformationVirtualMemory</b> returns STATUS_SUCCESS on success, or the appropriate NTSTATUS error code on failure.

## Remarks

The <b>ZwSetInformationVirtualMemory</b> routine is called by drivers that know the set of addresses they will be accessing. If it's likely that these addresses are no longer resident in memory (i.e. they have been paged out to disk), calling this routine on those address ranges before access reduces the overall latency because it efficiently brings in those address ranges from disk using large, concurrent I/O requests where possible.



<b>ZwSetInformationVirtualMemory</b> allows drivers to make efficient use of disk hardware by issuing large, concurrent I/Os where possible when the driver provides a list of process address ranges that are going to be accessed. Even for a single address range (e.g. a file mapping), the routine can provide performance improvements by issuing a single large I/O rather than the many smaller I/Os that would be issued via page faulting.



Drivers call this routine  purely for performance optimization: prefetching is not necessary for accessing the target address ranges. The prefetched memory is not added to the target process' working set; it is cached in physical memory. When the prefetched address ranges are accessed by the target process, they are added to the working set.



Because this call is  not necessary for correct operation of the driver, it is treated as a strong hint by the system and is subject to usual physical memory constraints where it can completely or partially fail under low-memory conditions. It can also create memory pressure if called with large address ranges, so applications should only prefetch address ranges they will actually use.
</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntddk.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | PowerIrpDDis, HwStorPortProhibitedDDIs |