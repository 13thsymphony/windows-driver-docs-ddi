---
UID: NF:ntddk.RtlIsRoot
title: RtlIsRoot macro
author: windows-driver-content
description: The RtlIsRoot routine determines whether the specified node is the root node of a splay link tree.
old-location: ifsk\rtlisroot.htm
old-project: ifsk
ms.assetid: 74b3894e-972f-430b-bb8f-20fa46bf8b7d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlIsRoot, RtlIsRoot routine [Installable File System Drivers], ifsk.rtlisroot, ntddk/RtlIsRoot, rtlref_d7c73e66-d8b8-4a18-a987-d61f13f48dc4.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	RtlIsRoot
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# RtlIsRoot function
The <b>RtlIsRoot</b> routine determines whether the specified node is the root node of a splay link tree.

## Syntax

````
BOOLEAN RtlIsRoot(
  _In_ PRTL_SPLAY_LINKS Links
);
````

## Parameters

`Links`

Pointer to the node. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>.


## Return Value

None

## Remarks

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlIsRoot</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the splay link tree or just-initialized node at <i>Links</i> is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntddk.h (include Ntddk.h, Ntifs.h) |
| **IRQL** | See Remarks section. |

## See Also

<a href="..\ntddk\nf-ntddk-rtlinitializesplaylinks.md">RtlInitializeSplayLinks</a>



<a href="..\ntddk\nf-ntddk-rtlisleftchild.md">RtlIsLeftChild</a>



<a href="..\ntddk\nf-ntddk-rtlisrightchild.md">RtlIsRightChild</a>