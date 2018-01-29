---
UID : NF:ntddk.RtlRightChild
title : RtlRightChild macro
author : windows-driver-content
description : The RtlRightChild routine returns a pointer to the right child of the specified splay link node.
old-location : ifsk\rtlrightchild.htm
old-project : ifsk
ms.assetid : 1b906983-b000-449b-8e82-46ade5384168
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : rtlref_be516cb5-c4a7-4eb7-8faa-eac591b0902d.xml, RtlRightChild routine [Installable File System Drivers], RtlRightChild, ntddk/RtlRightChild, ifsk.rtlrightchild
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ntddk.h
req.include-header : Ntddk.h, Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : 
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
req.lib : ntddk.h
req.dll : 
req.irql : See Remarks section.
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---


# RtlRightChild function
The <b>RtlRightChild</b> routine returns a pointer to the right child of the specified splay link node.

## Syntax

````
PRTL_SPLAY_LINKS RtlRightChild(
  _In_ PRTL_SPLAY_LINKS Links
);
````

## Parameters

`Links`

Pointer to the node whose right child is to be returned. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>.


## Return Value

None

## Remarks

<b>RtlRightChild</b> can be called repeatedly in conjunction with <b>RtlParent</b> and <b>RtlLeftChild</b> to walk a splay link tree. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlRightChild</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h (include Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | See Remarks section. |
| **DDI compliance rules** |  |

## See Also

<a href="..\ntddk\nf-ntddk-rtlinsertasrightchild.md">RtlInsertAsRightChild</a>

<a href="..\ntddk\nf-ntddk-rtlinitializesplaylinks.md">RtlInitializeSplayLinks</a>

<a href="..\ntddk\nf-ntddk-rtlparent.md">RtlParent</a>

<a href="..\ntddk\nf-ntddk-rtlleftchild.md">RtlLeftChild</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlRightChild routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>