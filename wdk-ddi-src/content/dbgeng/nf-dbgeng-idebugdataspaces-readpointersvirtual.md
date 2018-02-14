---
UID: NF:dbgeng.IDebugDataSpaces.ReadPointersVirtual
title: IDebugDataSpaces::ReadPointersVirtual method
author: windows-driver-content
description: The ReadPointersVirtual method is a convenience method for reading pointers from the target's virtual address space.
old-location: debugger\readpointersvirtual.htm
old-project: debugger
ms.assetid: 003fd20c-12d6-40b0-8e43-a7d730199846
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: IDebugDataSpaces3 interface [Windows Debugging], ReadPointersVirtual method, dbgeng/IDebugDataSpaces::ReadPointersVirtual, ReadPointersVirtual method [Windows Debugging], IDebugDataSpaces4 interface, dbgeng/IDebugDataSpaces3::ReadPointersVirtual, IDebugDataSpaces4::ReadPointersVirtual, IDebugDataSpaces2::ReadPointersVirtual, ReadPointersVirtual method [Windows Debugging], IDebugDataSpaces interface, IDebugDataSpaces, IDebugDataSpaces interface [Windows Debugging], ReadPointersVirtual method, IDebugDataSpaces3::ReadPointersVirtual, dbgeng/IDebugDataSpaces2::ReadPointersVirtual, IDebugDataSpaces::ReadPointersVirtual, IDebugDataSpaces2 interface [Windows Debugging], ReadPointersVirtual method, dbgeng/IDebugDataSpaces4::ReadPointersVirtual, IDebugDataSpaces_d3857a69-3e22-4d7a-97ef-d6cb7bf8613a.xml, ReadPointersVirtual method [Windows Debugging], IDebugDataSpaces3 interface, IDebugDataSpaces4 interface [Windows Debugging], ReadPointersVirtual method, debugger.readpointersvirtual, ReadPointersVirtual, ReadPointersVirtual method [Windows Debugging], IDebugDataSpaces2 interface, ReadPointersVirtual method [Windows Debugging]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugDataSpaces.ReadPointersVirtual
-	IDebugDataSpaces2.ReadPointersVirtual
-	IDebugDataSpaces3.ReadPointersVirtual
-	IDebugDataSpaces4.ReadPointersVirtual
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# ReadPointersVirtual method
The <b>ReadPointersVirtual</b> method is a convenience method for reading pointers from the target's virtual address space.

## Syntax

````
HRESULT ReadPointersVirtual(
  [in]  ULONG    Count,
  [in]  ULONG64  Offset,
  [out] PULONG64 Ptrs
);
````

## Parameters

`Count`

Specifies the number of pointers to read.

`Offset`

Specifies the location in the target's virtual address space to start reading the pointers.

`Ptrs`

Specifies the array to store the pointers.  The number of elements this array holds is <i>Count</i>.


## Return Value

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
All the pointers were read from the target's memory and stored in <i>Ptrs</i>.

</td>
</tr>
</table>
 

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

This method reads from the memory from the target's virtual address space.  The memory is then treated as a list of pointers.  Any 32-bit pointers are then sign-extended to  64-bit values.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces.md">IDebugDataSpaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554359">ReadVirtual</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561451">WritePointersVirtual</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces::ReadPointersVirtual method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>