---
UID: NF:dbgeng.IDebugSymbols3.Reload
title: IDebugSymbols3::Reload method
author: windows-driver-content
description: The Reload method deletes the engine's symbol information for the specified module and reload these symbols as needed.
old-location: debugger\reload.htm
old-project: debugger
ms.assetid: f739d5b8-80be-40e3-9139-93342c4fe458
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: Reload method [Windows Debugging], IDebugSymbols interface, Reload method [Windows Debugging], IDebugSymbols2 interface, Reload, IDebugSymbols_ec5df701-b081-45c4-b2e4-10c101ce69a4.xml, Reload method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols2 interface [Windows Debugging], Reload method, dbgeng/IDebugSymbols2::Reload, dbgeng/IDebugSymbols3::Reload, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], Reload method, IDebugSymbols::Reload, IDebugSymbols2::Reload, dbgeng/IDebugSymbols::Reload, IDebugSymbols interface [Windows Debugging], Reload method, Reload method [Windows Debugging], debugger.reload, IDebugSymbols3::Reload
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
-	IDebugSymbols.Reload
-	IDebugSymbols2.Reload
-	IDebugSymbols3.Reload
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# Reload method
The <b>Reload</b>  method deletes the engine's symbol information for the specified module and reload these symbols as needed.

## Syntax

````
HRESULT Reload(
  [in] PCSTR Module
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

<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564805">.reload (Reload Module)</a>

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols::Reload method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>