---
UID: NF:dbgeng.IDebugSymbols.GetOffsetTypeId
title: IDebugSymbols::GetOffsetTypeId method
author: windows-driver-content
description: The GetOffsetTypeId method returns the type ID of the symbol closest to the specified memory location.
old-location: debugger\getoffsettypeid.htm
old-project: Debugger
ms.assetid: cf533f21-90eb-46ec-860f-d12a8d40c430
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.getoffsettypeid, IDebugSymbols interface [Windows Debugging], GetOffsetTypeId method, IDebugSymbols::GetOffsetTypeId, IDebugSymbols2::GetOffsetTypeId, IDebugSymbols3::GetOffsetTypeId, IDebugSymbols_3f41981b-8ed2-4828-8bfb-a50b934a65ee.xml, GetOffsetTypeId method [Windows Debugging], IDebugSymbols2 interface [Windows Debugging], GetOffsetTypeId method, GetOffsetTypeId method [Windows Debugging], IDebugSymbols3 interface, dbgeng/IDebugSymbols2::GetOffsetTypeId, GetOffsetTypeId method [Windows Debugging], IDebugSymbols interface, GetOffsetTypeId, IDebugSymbols3 interface [Windows Debugging], GetOffsetTypeId method, dbgeng/IDebugSymbols3::GetOffsetTypeId, dbgeng/IDebugSymbols::GetOffsetTypeId, GetOffsetTypeId method [Windows Debugging], IDebugSymbols2 interface, IDebugSymbols
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
-	IDebugSymbols.GetOffsetTypeId
-	IDebugSymbols2.GetOffsetTypeId
-	IDebugSymbols3.GetOffsetTypeId
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetOffsetTypeId method
The <b>GetOffsetTypeId</b> method returns the type ID of the symbol closest to the specified memory location.

## Syntax

````
HRESULT GetOffsetTypeId(
  [in]            ULONG64  Offset,
  [out]           PULONG   TypeId,
  [out, optional] PULONG64 Module
);
````

## Parameters

`Offset`

Specifies the location in the target's memory for the symbol.  The symbol closest to this location is used.

`TypeId`

Receives the type ID of the symbol.

`Module`

Specifies the location in the target's memory address space of the base of the module to which the symbol belongs.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.  If <i>Module</i> is <b>NULL</b>, this information is not returned.


## Return Value

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
The method was successful

</td>
</tr>
</table>

## Remarks

For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549376">GetTypeId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549173">GetSymbolTypeId</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugSymbols::GetOffsetTypeId method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>