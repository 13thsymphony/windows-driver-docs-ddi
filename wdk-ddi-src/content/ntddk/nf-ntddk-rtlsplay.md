---
UID: NF:ntddk.RtlSplay
title: RtlSplay function
author: windows-driver-content
description: The RtlSplay routine rebalances, or &#0034;splays,&#0034; a splay link tree around the specified splay link, making that link the new root of the tree.
old-location: ifsk\rtlsplay.htm
old-project: ifsk
ms.assetid: b62834ec-6100-429a-b62f-7e30c58b13e5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RtlSplay, RtlSplay routine [Installable File System Drivers], ifsk.rtlsplay, ntddk/RtlSplay, rtlref_e44a955e-57eb-46f9-be07-9f658b8fd6db.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
-	RtlSplay
product:
- Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# RtlSplay function
The <b>RtlSplay</b> routine rebalances, or "splays," a splay link tree around the specified splay link, making that link the new root of the tree.

## Syntax

```
NTSYSAPI PRTL_SPLAY_LINKS RtlSplay(
  PRTL_SPLAY_LINKS Links
);
```

## Parameters

`Links`

A pointer to the node that is to become the root node of the rebalanced splay link tree. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>.


## Return Value

<b>RtlSplay</b> returns the <i>Links</i> pointer when it has rebalanced the tree.

## Remarks

If L is the given link, P is its parent node, and G is its grandparent node, <b>RtlSplay</b> rebalances a splay link tree according to one of the six patterns shown in the following figure.

<img alt="Diagram illustrating the rebalancing of a splay link tree, where L is the given link, P is its parent node, and G is its grandparent node" src="images/treeRtlSplay.gif"/>
Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlSplay</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | See Remarks section. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552201">RtlDelete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553010">RtlInitializeSplayLinks</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553017">RtlInsertAsLeftChild</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553022">RtlInsertAsRightChild</a>