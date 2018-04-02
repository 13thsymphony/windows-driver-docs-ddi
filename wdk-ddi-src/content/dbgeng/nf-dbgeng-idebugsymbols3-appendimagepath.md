---
UID: NF:dbgeng.IDebugSymbols3.AppendImagePath
title: IDebugSymbols3::AppendImagePath method
author: windows-driver-content
description: The AppendImagePath method appends directories to the executable image path.
old-location: debugger\appendimagepath.htm
old-project: debugger
ms.assetid: faafc6d0-f311-46c1-87c1-8b0ea20984db
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: AppendImagePath method [Windows Debugging], AppendImagePath method [Windows Debugging], IDebugSymbols interface, AppendImagePath method [Windows Debugging], IDebugSymbols2 interface, AppendImagePath method [Windows Debugging], IDebugSymbols3 interface, AppendImagePath,IDebugSymbols3.AppendImagePath, IDebugSymbols interface [Windows Debugging], AppendImagePath method, IDebugSymbols2 interface [Windows Debugging], AppendImagePath method, IDebugSymbols2::AppendImagePath, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], AppendImagePath method, IDebugSymbols3::AppendImagePath, IDebugSymbols::AppendImagePath, IDebugSymbols_ea3dc04a-42d9-4457-830d-5544f50c5a97.xml, dbgeng/IDebugSymbols2::AppendImagePath, dbgeng/IDebugSymbols3::AppendImagePath, dbgeng/IDebugSymbols::AppendImagePath, debugger.appendimagepath
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
-	Dbgeng.h
api_name:
-	IDebugSymbols.AppendImagePath
-	IDebugSymbols2.AppendImagePath
-	IDebugSymbols3.AppendImagePath
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugSymbols3::AppendImagePath method
The <b>AppendImagePath</b>  method appends directories to the executable image path.

## Syntax

```
HRESULT AppendImagePath(
  PCSTR Addition
);
```

## Parameters

`Addition`

Specifies the directories to append to the executable image path.  This is a string that contains directory names separated by semicolons (;).


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
The method was successful.

</td>
</tr>
</table>
 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

The executable image path is used by the <a href="https://msdn.microsoft.com/1e32bd40-8c77-4c6b-913c-6ec26707ed36">engine</a> when searching for executable images.

The executable image path can consist of several directories separated by semicolons (;).  These directories are searched in order.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546851">GetImagePath</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550856">IDebugSymbols</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550864">IDebugSymbols2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550870">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556708">SetImagePath</a>