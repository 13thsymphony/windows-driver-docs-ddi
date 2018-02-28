---
UID: NF:dbgeng.IDebugDataSpaces.WritePointersVirtual
title: IDebugDataSpaces::WritePointersVirtual method
author: windows-driver-content
description: The WritePointersVirtual method is a convenience method for writing pointers to the target's virtual address space.
old-location: debugger\writepointersvirtual.htm
old-project: debugger
ms.assetid: b6bde54b-262a-4431-8f85-63f9c66463c4
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: IDebugDataSpaces, IDebugDataSpaces interface [Windows Debugging], WritePointersVirtual method, IDebugDataSpaces2 interface [Windows Debugging], WritePointersVirtual method, IDebugDataSpaces2::WritePointersVirtual, IDebugDataSpaces3 interface [Windows Debugging], WritePointersVirtual method, IDebugDataSpaces3::WritePointersVirtual, IDebugDataSpaces4 interface [Windows Debugging], WritePointersVirtual method, IDebugDataSpaces4::WritePointersVirtual, IDebugDataSpaces::WritePointersVirtual, IDebugDataSpaces_da1045b5-8b82-4412-8e83-58c285dccce0.xml, WritePointersVirtual method [Windows Debugging], WritePointersVirtual method [Windows Debugging], IDebugDataSpaces interface, WritePointersVirtual method [Windows Debugging], IDebugDataSpaces2 interface, WritePointersVirtual method [Windows Debugging], IDebugDataSpaces3 interface, WritePointersVirtual method [Windows Debugging], IDebugDataSpaces4 interface, WritePointersVirtual,IDebugDataSpaces.WritePointersVirtual, dbgeng/IDebugDataSpaces2::WritePointersVirtual, dbgeng/IDebugDataSpaces3::WritePointersVirtual, dbgeng/IDebugDataSpaces4::WritePointersVirtual, dbgeng/IDebugDataSpaces::WritePointersVirtual, debugger.writepointersvirtual
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugDataSpaces.WritePointersVirtual
-	IDebugDataSpaces2.WritePointersVirtual
-	IDebugDataSpaces3.WritePointersVirtual
-	IDebugDataSpaces4.WritePointersVirtual
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# WritePointersVirtual method
The <b>WritePointersVirtual</b> method is a convenience method for writing pointers to the target's virtual address space.

## Syntax

````
HRESULT WritePointersVirtual(
  [in] ULONG    Count,
  [in] ULONG64  Offset,
  [in] PULONG64 Ptrs
);
````

## Parameters

`Count`

Specifies the number of pointers to write.

`Offset`

Specifies the location in the target's virtual address space at which to start writing the pointers.

`Ptrs`

Specifies the array of pointers to write.  The number of elements in this array is <i>Count</i>.


## Return Value

This method can also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
All the pointers in <i>Ptrs</i>  were written to the target's memory.

</td>
</tr>
</table>

## Remarks

If the target uses 32-bit pointers, this method casts the specified  64-bit values into 32-bit pointers.  Then it writes these pointers to the target's memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugdataspaces.md">IDebugDataSpaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561468">WriteVirtual</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces4.md">IDebugDataSpaces4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554323">ReadPointersVirtual</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces3.md">IDebugDataSpaces3</a>



<a href="..\dbgeng\nn-dbgeng-idebugdataspaces2.md">IDebugDataSpaces2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugDataSpaces::WritePointersVirtual method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>