---
UID: NF:wdm.MmUnmapLockedPages
title: MmUnmapLockedPages function
author: windows-driver-content
description: The MmUnmapLockedPages routine releases a mapping that was set up by a preceding call to the MmMapLockedPages or MmMapLockedPagesSpecifyCache routine.
old-location: kernel\mmunmaplockedpages.htm
old-project: kernel
ms.assetid: ab5f33b9-5261-4d30-bceb-8e91a24ae0a8
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: MmUnmapLockedPages, MmUnmapLockedPages routine [Kernel-Mode Driver Architecture], k106_1ed6ae95-665b-4a6e-802a-4f80294c4f6e.xml, kernel.mmunmaplockedpages, wdm/MmUnmapLockedPages
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmUnmapLockedPages
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# MmUnmapLockedPages function
The <b>MmUnmapLockedPages</b> routine releases a mapping that was set up by a preceding call to the <a href="..\wdm\nf-wdm-mmmaplockedpages.md">MmMapLockedPages</a> or <a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a> routine.

## Syntax

````
VOID MmUnmapLockedPages(
  _In_ PVOID BaseAddress,
  _In_ PMDL  MemoryDescriptorList
);
````

## Parameters

`BaseAddress`

Pointer to the base virtual address to which the physical pages were mapped.

`MemoryDescriptorList`

Pointer to an MDL.


## Return Value

None

## Remarks

Callers of <b>MmUnmapLockedPages</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the pages were mapped to system space. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.

Note that if the call to <b>MmMapLockedPages</b> or <b>MmMapLockedPagesSpecifyCache</b> specified user mode, the caller must be in the context of the original process before calling <b>MmUnmapLockedPages</b>. This is because the unmapping operation occurs in the context of the calling process, and, if the context is incorrect, the unmapping operation could delete the address range of a random process.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | See Remarks section. |
| **DDI compliance rules** | HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-mmmaplockedpages.md">MmMapLockedPages</a>



<a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a>