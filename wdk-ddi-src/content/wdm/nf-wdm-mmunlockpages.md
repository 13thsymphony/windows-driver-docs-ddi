---
UID: NF:wdm.MmUnlockPages
title: MmUnlockPages function
author: windows-driver-content
description: The MmUnlockPages routine unlocks the physical pages that are described by the specified memory descriptor list (MDL).
old-location: kernel\mmunlockpages.htm
old-project: kernel
ms.assetid: 506f5fef-11fa-4d65-a180-c613cd8a8e1e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: MmUnlockPages, MmUnlockPages routine [Kernel-Mode Driver Architecture], k106_b8d8a984-9e0e-4322-bce1-2dd79e8d3a10.xml, kernel.mmunlockpages, wdm/MmUnlockPages
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmUnlockPages
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# MmUnlockPages function
The <b>MmUnlockPages</b> routine unlocks the physical pages that are described by the specified memory descriptor list (MDL).

## Syntax

````
VOID MmUnlockPages(
  _Inout_ PMDL MemoryDescriptorList
);
````

## Parameters

`MemoryDescriptorList`

A pointer to an MDL.


## Return Value

None

## Remarks

The memory described by the specified MDL must have been locked previously by a call to <a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a>. If the specified MDL is mapped to system address space, <b>MmUnlockPages</b> releases this mapping before it unlocks the pages.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmUnlockPages routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>