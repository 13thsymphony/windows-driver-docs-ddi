---
UID: NF:dbgeng.IDebugSymbols2.GetTypeName
title: IDebugSymbols2::GetTypeName method
author: windows-driver-content
description: The GetTypeName method returns the name of the type symbol specified by its type ID and module.
old-location: debugger\gettypename.htm
old-project: debugger
ms.assetid: 09aa3ba9-d5b6-4c08-93f1-f7beca9350a1
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetTypeName method [Windows Debugging], GetTypeName method [Windows Debugging], IDebugSymbols interface, GetTypeName method [Windows Debugging], IDebugSymbols2 interface, GetTypeName method [Windows Debugging], IDebugSymbols3 interface, GetTypeName,IDebugSymbols2.GetTypeName, IDebugSymbols interface [Windows Debugging], GetTypeName method, IDebugSymbols2, IDebugSymbols2 interface [Windows Debugging], GetTypeName method, IDebugSymbols2::GetTypeName, IDebugSymbols3 interface [Windows Debugging], GetTypeName method, IDebugSymbols3::GetTypeName, IDebugSymbols::GetTypeName, IDebugSymbols_01f0496a-ce0e-442b-88c9-2a92c15a1237.xml, dbgeng/IDebugSymbols2::GetTypeName, dbgeng/IDebugSymbols3::GetTypeName, dbgeng/IDebugSymbols::GetTypeName, debugger.gettypename
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
req.lib: 
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
-	IDebugSymbols.GetTypeName
-	IDebugSymbols2.GetTypeName
-	IDebugSymbols3.GetTypeName
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugSymbols2::GetTypeName method
The <b>GetTypeName</b>  method returns the name of the type symbol specified by its type ID and module.

## Syntax

```
HRESULT GetTypeName(
  ULONG64 Module,
  ULONG   TypeId,
  PSTR    NameBuffer,
  ULONG   NameBufferSize,
  PULONG  NameSize
);
```

## Parameters

`Module`

Specifies the base address of the module to which the type belongs.  For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff552231">Modules</a>.

`TypeId`

Specifies the type ID of the type.

`NameBuffer`

Receives the name of the type.  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.

`NameBufferSize`

Specifies the size in characters of the buffer <i>NameBuffer</i>.

`NameSize`

Receives the size in characters of the type's name.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.


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
The method was successful. However, the buffer was not large enough to hold the name of the type and it was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL </b></dt>
</dl>
</td>
<td width="60%">
The specified type could not be found in the specified module.

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

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549457">GetTypeSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>