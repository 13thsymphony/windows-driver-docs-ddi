---
UID: NF:dbgeng.IDebugClient5.SetOutputLinePrefixWide
title: IDebugClient5::SetOutputLinePrefixWide method
author: windows-driver-content
description: Sets a wide string prefix for output lines.
old-location: debugger\idebugclient5_setoutputlineprefixwide.htm
old-project: debugger
ms.assetid: B847EE03-65C0-4046-BD0A-0441C487056F
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugClient5, IDebugClient5 interface [Windows Debugging], SetOutputLinePrefixWide method, IDebugClient5::SetOutputLinePrefixWide, SetOutputLinePrefixWide method [Windows Debugging], SetOutputLinePrefixWide method [Windows Debugging], IDebugClient5 interface, SetOutputLinePrefixWide,IDebugClient5.SetOutputLinePrefixWide, dbgeng/IDebugClient5::SetOutputLinePrefixWide, debugger.idebugclient5_setoutputlineprefixwide
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
-	dbgeng.h
api_name:
-	IDebugClient5.SetOutputLinePrefixWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# SetOutputLinePrefixWide method
Sets a wide string prefix for output lines.

## Syntax

````
HRESULT SetOutputLinePrefixWide(
  [in, optional] PCWSTR Prefix
);
````

## Parameters

`Prefix`

The pointer to a Unicode character prefix string.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugclient5.md">IDebugClient5</a>