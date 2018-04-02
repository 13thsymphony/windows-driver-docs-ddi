---
UID: NF:wdbgexts.ReloadSymbols
title: ReloadSymbols function
author: windows-driver-content
description: The ReloadSymbols function deletes symbol information from the debugger so that it can be reloaded as needed. This function behaves the same way as the debugger command .reload.
old-location: debugger\reloadsymbols.htm
old-project: debugger
ms.assetid: 5778f57c-52dd-43f4-b0f7-d07e0c40512b
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: ReloadSymbols, ReloadSymbols function [Windows Debugging], WdbgExts_Ref_c48c63b8-6c59-42f7-8a44-78462cbf653f.xml, debugger.reloadsymbols, wdbgexts/ReloadSymbols
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
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
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	ReloadSymbols
product:
- Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---


# ReloadSymbols function
The <b>ReloadSymbols</b> function deletes symbol information from the debugger so that it can be reloaded as needed.  This function behaves the same way as the debugger command <a href="https://msdn.microsoft.com/750eb1a2-7af9-4f2d-81ca-9ea0fb157961">.reload</a>.

## Syntax

```
void ReloadSymbols(
  PSTR Arg OPTIONAL
);
```

## Parameters

`OPTIONAL`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564805">.reload (Reload Module)</a>