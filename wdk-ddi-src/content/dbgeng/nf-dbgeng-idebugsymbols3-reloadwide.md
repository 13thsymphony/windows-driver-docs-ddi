---
UID: NF:dbgeng.IDebugSymbols3.ReloadWide
title: IDebugSymbols3::ReloadWide method
author: windows-driver-content
description: The ReloadWide method deletes the engine's symbol information for the specified module and reload these symbols as needed.
old-location: debugger\reloadwide.htm
old-project: debugger
ms.assetid: 3975bc55-15e3-45ca-82df-76c5ed3b0086
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: ReloadWide method [Windows Debugging], IDebugSymbols3 interface, dbgeng/IDebugSymbols3::ReloadWide, IDebugSymbols3::ReloadWide, IDebugSymbols3 interface [Windows Debugging], ReloadWide method, debugger.reloadwide, ReloadWide, IDebugSymbols3, ReloadWide method [Windows Debugging]
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
-	IDebugSymbols3.ReloadWide
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# ReloadWide method
The <b>ReloadWide</b>  method deletes the engine's symbol information for the specified module and reload these symbols as needed.

## Syntax

````
HRESULT ReloadWide(
  [in] PCWSTR Module
);
````

## Parameters

`Module`

Specifies the module to reload.


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
The method was successful

</td>
</tr>
</table> 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

## Remarks

This method behaves the same way as the debugger command <b>.reload</b>.  The <i>Module</i> parameter is treated the same way as the arguments to <b>.reload</b>.  For example, setting the <i>Module</i> parameter to "/u ntdll.dll" has the same effect as the command <b>.reload /u ntdll.dll</b>.

For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564805">.reload (Reload Module)</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::ReloadWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>