---
UID: NF.dbgeng.IDebugSymbols3.GetScope
title: IDebugSymbols3::GetScope method
author: windows-driver-content
description: The GetScope method returns information about the current scope.
old-location: debugger\getscope.htm
old-project: Debugger
ms.assetid: 59eb490e-66d5-4108-8d00-5503fa56665d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IDebugSymbols3, IDebugSymbols3::GetScope, GetScope
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h, Ntddk.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugSymbols.GetScope,IDebugSymbols2.GetScope,IDebugSymbols3.GetScope
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
---

# IDebugSymbols3::GetScope method



## -description
The <b>GetScope</b> method returns information about the current scope.



## -syntax

````
HRESULT GetScope(
  [out, optional] PULONG64           InstructionOffset,
  [out, optional] PDEBUG_STACK_FRAME ScopeFrame,
  [out, optional] PVOID              ScopeContext,
  [in]            ULONG              ScopeContextSize
);
````


## -parameters

### -param InstructionOffset [out, optional]

Receives the location in the process's virtual address space of the current scope's current instruction.


### -param ScopeFrame [out, optional]

Receives the <a href="debugger.debug_stack_frame">DEBUG_STACK_FRAME</a> structure representing the current scope's stack frame.


### -param ScopeContext [out, optional]

Receives the current scope's <a href="debugger.scopes_and_symbol_groups#thread_context#thread_context">thread context</a>.  The type of the thread context is the CONTEXT structure for the target's effective processor.  The buffer <i>ScopeContext</i> must be large enough to hold this structure.


### -param ScopeContextSize [in]

Specifies the size of the buffer <i>ScopeContext</i>.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>The size of the buffer <i>ScopeContext</i> was not large enough to hold the scope's context.

 


## -remarks
For more information about scopes, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h or Ntddk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols.md">IDebugSymbols</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols2.md">IDebugSymbols2</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="debugger.geteffectiveprocessortype">IDebugControl::GetEffectiveProcessorType</a>
</dt>
<dt>
<a href="debugger.resetscope">ResetScope</a>
</dt>
<dt>
<a href="debugger.setscope">SetScope</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugSymbols::GetScope method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

