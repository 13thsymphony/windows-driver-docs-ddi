---
UID : NF:ntddk.RtlDeleteNoSplay
title : RtlDeleteNoSplay function
author : windows-driver-content
description : The RtlDeleteNoSplay routine deletes the specified node from the splay link tree.
old-location : ifsk\rtldeletenosplay.htm
old-project : ifsk
ms.assetid : 09d8096a-71f9-4e9d-a66b-282424394b76
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : RtlDeleteNoSplay
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RtlDeleteNoSplay
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : See Remarks section.
req.typenames : WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# RtlDeleteNoSplay function
The <b>RtlDeleteNoSplay</b> routine deletes the specified node from the splay link tree.

## Syntax

````
VOID RtlDeleteNoSplay(
  _In_    PRTL_SPLAY_LINKS Links,
  _Inout_ PRTL_SPLAY_LINKS *Root
);
````

## Parameters

`Links`

A pointer to the node to be deleted. The node must have been initialized by calling <b>RtlInitializeSplayLinks</b>.

`Root`

A pointer to the caller's pointer to the root node of the splay link tree. The caller's pointer is updated after the node is deleted.


## Return Value

None

## Remarks

Unlike <b>RtlDelete</b>, <b>RtlDeleteNoSplay</b> does not rebalance the splay link tree after the node is deleted. 

Callers of the <b>Rtl</b> splay link routines are responsible for synchronizing access to the splay link tree. A fast mutex is the most efficient synchronization mechanism to use for this purpose. 

Callers of <b>RtlDeleteNoSplay</b> must be running at IRQL &lt;= DISPATCH_LEVEL if the splay link tree is nonpaged. Usually, callers are running at IRQL PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h (include Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | See Remarks section. |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntddk\nf-ntddk-rtldelete.md">RtlDelete</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinitializesplaylinks.md">RtlInitializeSplayLinks</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinsertasleftchild.md">RtlInsertAsLeftChild</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlinsertasrightchild.md">RtlInsertAsRightChild</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlsplay.md">RtlSplay</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlDeleteNoSplay routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>