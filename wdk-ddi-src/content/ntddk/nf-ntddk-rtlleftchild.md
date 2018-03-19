---
UID: NF:ntddk.RtlLeftChild
title: RtlLeftChild macro
author: windows-driver-content
description: The RtlLeftChild routine returns a pointer to the left child of the specified splay link node.
old-location: ifsk\rtlleftchild.htm
old-project: ifsk
ms.assetid: 26e6b0c6-7de0-43c9-a117-5c0bf0e986a2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlLeftChild, RtlLeftChild routine [Installable File System Drivers], ifsk.rtlleftchild, ntddk/RtlLeftChild, rtlref_f2bfae7c-de1d-4d7c-84b5-947a0cfdb16f.xml
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
-	RtlLeftChild
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# RtlLeftChild function
The <b>RtlLeftChild</b> routine returns a pointer to the left child of the specified splay link node.

## Syntax

````
PRTL_SPLAY_LINKS RtlLeftChild(
  _In_ PRTL_SPLAY_LINKS Links
);
````

## Parameters

`Links`

Pointer to the node whose left child is to be returned. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>.


## Return Value

None

## Remarks

<b>RtlLeftChild</b> can be called repeatedly in conjunction with <b>RtlParent</b> and <b>RtlRightChild</b> to walk a splay link tree. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlLeftChild</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | ntddk.h (include Ntddk.h, Ntifs.h) |
| **IRQL** | See Remarks section. |

## See Also

<a href="..\ntddk\nf-ntddk-rtlinitializesplaylinks.md">RtlInitializeSplayLinks</a>



<a href="..\ntddk\nf-ntddk-rtlparent.md">RtlParent</a>



<a href="..\ntddk\nf-ntddk-rtlrightchild.md">RtlRightChild</a>



<a href="..\ntddk\nf-ntddk-rtlinsertasleftchild.md">RtlInsertAsLeftChild</a>