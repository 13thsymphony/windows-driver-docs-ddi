---
UID: NC:dbgeng.PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK
title: PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK
author: windows-driver-content
description: The ReconstructStack callback function queries dump stream provider on a per-thread basis.
old-location: debugger\reconstructstack.htm
old-project: debugger
ms.assetid: 639A90E8-4B2D-413B-B6F9-078C9DF1B02F
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK, ReconstructStack, ReconstructStack callback function [Windows Debugging], dbgeng/ReconstructStack, debugger.reconstructstack
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
-	ReconstructStack
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK callback function
The <i>ReconstructStack</i> callback function queries dump stream provider on a per-thread basis.
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre> CALLBACK* PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK ReconstructStack;</pre>
</td>
</tr>
</table></span></div>

## Syntax

```
PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK PdebugStackProviderReconstructstack;

HRESULT PdebugStackProviderReconstructstack(
  ULONG SystemThreadId,
  PDEBUG_STACK_FRAME_EX NativeFrames,
  ULONG CountNativeFrames,
  PSTACK_SYM_FRAME_INFO *StackSymFrames,
  PULONG StackSymFramesFilled
)
{...}
```

## Parameters

`SystemThreadId`

A system thread ID.

`NativeFrames`

Native frames.

`CountNativeFrames`

Specifies the number of native frames.

`*StackSymFrames`

A pointer to a symbol frames stack.

`StackSymFramesFilled`

Symbol frames stack filled value.


## Return Value

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

This function returns stack frames and symbolic data.

New in-line frames may be provided.

Stack dump provider must be enabled.

<i>ReconstructStack</i> is called <b>PDEBUG_STACK_PROVIDER_RECONSTRUCTSTACK</b>  in the Dbgeng.h header file.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |