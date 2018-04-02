---
UID: NC:dbgeng.PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES
title: PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES
author: windows-driver-content
description: The FreeStackSymFrames callback function frees memory from a stack provider.
old-location: debugger\freestacksymframes.htm
old-project: debugger
ms.assetid: E66742D4-A972-4096-8DDC-E8F42E8B8D25
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: FreeStackSymFrames, FreeStackSymFrames callback function [Windows Debugging], PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES, dbgeng/FreeStackSymFrames, debugger.freestacksymframes
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	UserDefined
api_location:
-	Dbgeng.h
api_name:
-	FreeStackSymFrames
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES callback function
The <i>FreeStackSymFrames</i> callback function frees memory from a stack provider.
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre> CALLBACK* PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES FreeStackSymFrames;</pre>
</td>
</tr>
</table></span></div>

## Syntax

```
PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES PdebugStackProviderFreestacksymframes;

HRESULT PdebugStackProviderFreestacksymframes(
  PSTACK_SYM_FRAME_INFO StackSymFrames
)
{...}
```

## Parameters

`StackSymFrames`

A stack to free.


## Return Value

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

After <i>FreeStackSymFrames</i> is called, the debugger calls the stack provider to free memory.

<i>FreeStackSymFrames</i> is called <b>PDEBUG_STACK_PROVIDER_FREESTACKSYMFRAMES</b>   in the Dbgeng.h header file.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/76984F28-7AC9-44FD-9D8B-CC184484C73E">EndThreadStackReconstruction</a>