---
UID: NF:wdm.MmFreePagesFromMdl
title: MmFreePagesFromMdl function
author: windows-driver-content
description: The MmFreePagesFromMdl routine frees all the physical pages that are described by an MDL that was created by the MmAllocatePagesForMdl routine.
old-location: kernel\mmfreepagesfrommdl.htm
old-project: kernel
ms.assetid: bde26b75-9eae-494b-b943-f1e9534c5f7a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: MmFreePagesFromMdl, kernel.mmfreepagesfrommdl, wdm/MmFreePagesFromMdl, MmFreePagesFromMdl routine [Kernel-Mode Driver Architecture], k106_4263f517-edab-4378-b316-ce344676d7e6.xml
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
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmFreePagesFromMdl
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# MmFreePagesFromMdl function
The <b>MmFreePagesFromMdl</b> routine frees all the physical pages that are described by an MDL that was created by the <a href="..\wdm\nf-wdm-mmallocatepagesformdl.md">MmAllocatePagesForMdl</a> routine.

## Syntax

````
VOID MmFreePagesFromMdl(
  _In_ PMDLX MemoryDescriptorList
);
````

## Parameters

`MemoryDescriptorList`

Pointer to an MDL that was created by <b>MmAllocatePagesForMdl</b>.


## Return Value

None

## Remarks

<b>MmFreePagesFromMdl</b> can only be used to free the memory pages that are described by an MDL that was created by <b>MmAllocatePagesForMdl</b>.

After calling <b>MmFreePagesFromMdl</b>, the caller must also call <a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a> to release the memory that was allocated for the MDL structure.

<b>MmFreePagesFromMdl</b> runs at IRQL &lt;= APC_LEVEL. For Windows Server 2008 and later versions of the Windows operating system, you can also call this routine at DISPATCH_LEVEL. However, you can improve driver performance by calling at IRQL &lt;= APC_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | See Remarks section. |
| **DDI compliance rules** | IrqlMmApcLte, HwStorPortProhibitedDDIs |

## See Also

<a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>



<a href="..\wdm\nf-wdm-mmallocatepagesformdl.md">MmAllocatePagesForMdl</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmFreePagesFromMdl routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>