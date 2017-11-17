---
UID: NF.dbgeng.IDebugAdvanced3.SetThreadContext
title: IDebugAdvanced3::SetThreadContext
author: windows-driver-content
description: The SetThreadContext method sets the current thread context.
old-location: debugger\setthreadcontext.htm
ms.assetid: eaaaa9d7-ba6d-4379-b721-74c92375ea05
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: debugger
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugAdvanced.SetThreadContext,IDebugAdvanced2.SetThreadContext,IDebugAdvanced3.SetThreadContext
req.alt-loc: dbgeng.h
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
ms.keywords: IDebugAdvanced3, SetThreadContext, IDebugAdvanced3::SetThreadContext
req.iface: IDebugAdvanced3
---

# IDebugAdvanced3::SetThreadContext method



## -description
<p>The <b>SetThreadContext</b> method sets the current <a href="debugger.scopes_and_symbol_groups#thread_context#thread_context">thread context</a>.</p>


## -syntax

````
HRESULT SetThreadContext(
  [in] PVOID Context,
  [in] ULONG ContextSize
);
````


## -parameters
<dl>

### -param <i>Context</i> [in]

<dd>
<p>Specifies the thread context. The type of the thread context is the CONTEXT structure for the target's effective processor.  The buffer <i>Context</i> must be large enough to hold this structure.</p>
</dd>

### -param <i>ContextSize</i> [in]

<dd>
<p>Specifies the size of the buffer <i>Context</i>.</p>
</dd>
</dl>

## -returns
<p>This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.</p><dl>
<dt><b>S_OK</b></dt>
</dl><p>The method was successful.</p>

<p> </p>

## -remarks
<p>For more information about the thread context, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.</p>

<p>For more information about the thread context, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549798">IDebugAdvanced</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549803">IDebugAdvanced2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549807">IDebugAdvanced3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556773">SetScope</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549291">GetThreadContext</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugAdvanced::SetThreadContext method%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
