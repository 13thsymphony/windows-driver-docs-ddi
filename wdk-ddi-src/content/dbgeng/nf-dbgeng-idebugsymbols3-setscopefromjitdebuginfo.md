---
UID: NF:dbgeng.IDebugSymbols3.SetScopeFromJitDebugInfo
title: IDebugSymbols3::SetScopeFromJitDebugInfo method
author: windows-driver-content
description: Recovers just-in-time (JIT) debugging information and sets current debugger scope context based on that information.
old-location: debugger\idebugsymbols3_setscopefromjitdebuginfo.htm
old-project: debugger
ms.assetid: 75417373-AA1B-4297-863A-00EA97069573
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], SetScopeFromJitDebugInfo method, IDebugSymbols3::SetScopeFromJitDebugInfo, SetScopeFromJitDebugInfo method [Windows Debugging], SetScopeFromJitDebugInfo method [Windows Debugging], IDebugSymbols3 interface, SetScopeFromJitDebugInfo,IDebugSymbols3.SetScopeFromJitDebugInfo, dbgeng/IDebugSymbols3::SetScopeFromJitDebugInfo, debugger.idebugsymbols3_setscopefromjitdebuginfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
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
-	IDebugSymbols3.SetScopeFromJitDebugInfo
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# SetScopeFromJitDebugInfo method
Recovers just-in-time (JIT) debugging information and sets current
    debugger scope context based on that information.

## Syntax

````
HRESULT SetScopeFromJitDebugInfo(
  [in] ULONG   OutputControl,
  [in] ULONG64 InfoOffset
);
````

## Parameters

`OutputControl`

An output control.

`InfoOffset`

An offset for the debugging information.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

The method gets JUT debugging information from   a specified address from the debugging target, and then sets the current
    debugger scope context from that information. 

This method is equivalent to '.jdinfo' command.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::SetScopeFromJitDebugInfo method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>