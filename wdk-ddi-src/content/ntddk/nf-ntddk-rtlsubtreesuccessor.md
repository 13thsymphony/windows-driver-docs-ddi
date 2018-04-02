---
UID: NF:ntddk.RtlSubtreeSuccessor
title: RtlSubtreeSuccessor function
author: windows-driver-content
description: The RtlSubtreeSuccessor routine returns a pointer to the successor of the specified node within the subtree that is rooted at that node.
old-location: ifsk\rtlsubtreesuccessor.htm
old-project: ifsk
ms.assetid: de592c2a-6f52-48ef-b2ee-253d83cafa80
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlSubtreeSuccessor, RtlSubtreeSuccessor routine [Installable File System Drivers], ifsk.rtlsubtreesuccessor, ntddk/RtlSubtreeSuccessor, rtlref_65e50284-427f-47d9-92c7-719b8bc1bab5.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 and later.
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlSubtreeSuccessor
product:
- Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# RtlSubtreeSuccessor function
The <b>RtlSubtreeSuccessor</b> routine returns a pointer to the successor of the specified node within the subtree that is rooted at that node.

## Syntax

```
NTSYSAPI PRTL_SPLAY_LINKS RtlSubtreeSuccessor(
  PRTL_SPLAY_LINKS Links
);
```

## Parameters

`Links`

A pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>.


## Return Value

<b>RtlSubtreeSuccessor</b> returns a pointer to the subtree successor of the node at <i>Links</i>, or <b>NULL</b> if the given node has no subtree successor.

## Remarks

If the node at <i>Links</i> has a right subtree, the leftmost node of that subtree is the subtree successor. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlSubtreeSuccessor</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the tree is nonpaged. If the tree is paged, callers must be running at IRQL &lt; DISPATCH_LEVEL. Usually callers are running at IRQL PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This routine is available on Microsoft Windows 2000 and later.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | See Remarks section. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553010">RtlInitializeSplayLinks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553188">RtlRealSuccessor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553226">RtlSplay</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553237">RtlSubtreePredecessor</a>