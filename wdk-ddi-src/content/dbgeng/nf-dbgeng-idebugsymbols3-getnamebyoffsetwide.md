---
UID : NF:dbgeng.IDebugSymbols3.GetNameByOffsetWide
title : IDebugSymbols3::GetNameByOffsetWide method
author : windows-driver-content
description : The GetNameByOffsetWide method returns the name of the symbol at the specified location in the target's virtual address space.
old-location : debugger\getnamebyoffsetwide.htm
old-project : debugger
ms.assetid : 45a041c9-029a-4fa1-91c6-562e56a30b3e
ms.author : windowsdriverdev
ms.date : 1/19/2018
ms.keywords : IDebugSymbols3 interface [Windows Debugging], GetNameByOffsetWide method, GetNameByOffsetWide, IDebugSymbols3::GetNameByOffsetWide, debugger.getnamebyoffsetwide, GetNameByOffsetWide method [Windows Debugging], dbgeng/IDebugSymbols3::GetNameByOffsetWide, IDebugSymbols3, GetNameByOffsetWide method [Windows Debugging], IDebugSymbols3 interface
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
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
req.lib : dbgeng.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetNameByOffsetWide method
The <b>GetNameByOffsetWide</b>  method returns the name of the symbol at the specified location in the target's virtual address space.

## Syntax

````
HRESULT GetNameByOffsetWide(
  [in]            ULONG64  Offset,
  [out, optional] PWSTR    NameBuffer,
  [in]            ULONG    NameBufferSize,
  [out, optional] PULONG   NameSize,
  [out, optional] PULONG64 Displacement
);
````

## Parameters

`Offset`

Specifies the location in the target's virtual address space of the symbol whose name is requested.  <i>Offset</i> does not need to specify the base location of the symbol; it only needs to specify a location within the symbol's memory allocation.

`NameBuffer`

Receives the symbol's name.  The name is qualified by the module to which the symbol belongs (for example, <b>mymodule!main</b>).  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.

`NameBufferSize`

Specifies the size in characters of the buffer <i>NameBuffer</i>.

`NameSize`

Receives the size in characters of the symbol's name.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.

`Displacement`

Receives the difference between the value of <i>Offset</i> and the base location of the symbol.  If <i>Displacement</i> is <b>NULL</b>, this information is not returned.


## Return Value

This method may also return other error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
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
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful.  However, the buffer was not large enough to hold the symbol's name, so it was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
No symbol could be found at the specified location.

</td>
</tr>
</table>

## Remarks

For more information about symbols and symbol names, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547204">GetNearNameByOffset</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548035">GetOffsetByName</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetNameByOffsetWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>