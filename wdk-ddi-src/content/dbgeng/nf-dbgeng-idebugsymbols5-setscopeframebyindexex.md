---
UID: NF:dbgeng.IDebugSymbols5.SetScopeFrameByIndexEx
title: IDebugSymbols5::SetScopeFrameByIndexEx method
author: windows-driver-content
description: Sets the current frame by using an index.
old-location: debugger\idebugsymbols5_setscopeframebyindexex.htm
old-project: debugger
ms.assetid: E0638C55-4160-48A5-9378-6AA9AAC8DC36
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugSymbols5, IDebugSymbols5 interface [Windows Debugging], SetScopeFrameByIndexEx method, IDebugSymbols5::SetScopeFrameByIndexEx, SetScopeFrameByIndexEx method [Windows Debugging], SetScopeFrameByIndexEx method [Windows Debugging], IDebugSymbols5 interface, SetScopeFrameByIndexEx,IDebugSymbols5.SetScopeFrameByIndexEx, dbgeng/IDebugSymbols5::SetScopeFrameByIndexEx, debugger.idebugsymbols5_setscopeframebyindexex
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
-	IDebugSymbols5.SetScopeFrameByIndexEx
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# SetScopeFrameByIndexEx method
Sets the current frame by using an index.

## Syntax

````
HRESULT SetScopeFrameByIndexEx(
  [in] ULONG Flags,
  [in] ULONG Index
);
````

## Parameters

`Flags`

A bit-set that contains options that affect the behavior of this method.

`Index`

An index by which to set the frame.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols5.md">IDebugSymbols5</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols5::SetScopeFrameByIndexEx method%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>