---
UID: NF:wdm.MmFreeMappingAddress
title: MmFreeMappingAddress function
author: windows-driver-content
description: The MmFreeMappingAddress routine frees a range of virtual memory reserved by the MmAllocateMappingAddress routine.
old-location: kernel\mmfreemappingaddress.htm
old-project: kernel
ms.assetid: df5afc18-da83-46b4-b7ab-8cef4353b951
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: MmFreeMappingAddress, MmFreeMappingAddress routine [Kernel-Mode Driver Architecture], k106_fa09359d-0552-429a-b3af-048f03ea7a15.xml, kernel.mmfreemappingaddress, wdm/MmFreeMappingAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmFreeMappingAddress
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# MmFreeMappingAddress function
The <b>MmFreeMappingAddress</b> routine frees a range of virtual memory reserved by the <a href="..\wdm\nf-wdm-mmallocatemappingaddress.md">MmAllocateMappingAddress</a> routine.

## Syntax

````
VOID MmFreeMappingAddress(
  _In_ PVOID BaseAddress,
  _In_ ULONG PoolTag
);
````

## Parameters

`BaseAddress`

Pointer to the beginning of the reserved memory buffer to free. This must be an address previously returned by <a href="..\wdm\nf-wdm-mmallocatemappingaddress.md">MmAllocateMappingAddress</a>.

`PoolTag`

Specifies the pool tag for the reserved memory buffer. This must be identical to the value specified in the <i>PoolTag</i> parameter of the call to <a href="..\wdm\nf-wdm-mmallocatemappingaddress.md">MmAllocateMappingAddress</a> that reserved the buffer.


## Return Value

None

## Remarks

<b>MmFreeMappingAddress</b> frees a range of memory reserved by <a href="..\wdm\nf-wdm-mmallocatemappingaddress.md">MmAllocateMappingAddress</a>. If the memory range has already been mapped by <a href="..\wdm\nf-wdm-mmmaplockedpageswithreservedmapping.md">MmMapLockedPagesWithReservedMapping</a>, it must first be unmapped with <a href="..\wdm\nf-wdm-mmunmapreservedmapping.md">MmUnmapReservedMapping</a> before the memory range can be freed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<=APC_LEVEL" |

## See Also

<a href="..\wdm\nf-wdm-mmallocatemappingaddress.md">MmAllocateMappingAddress</a>



<a href="..\wdm\nf-wdm-mmunmapreservedmapping.md">MmUnmapReservedMapping</a>



<a href="..\wdm\nf-wdm-mmmaplockedpageswithreservedmapping.md">MmMapLockedPagesWithReservedMapping</a>