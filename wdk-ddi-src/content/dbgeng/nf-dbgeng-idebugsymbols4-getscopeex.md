---
UID: NF:dbgeng.IDebugSymbols4.GetScopeEx
title: IDebugSymbols4::GetScopeEx method
author: windows-driver-content
description: Gets the scope as an extended frame structure.
old-location: debugger\idebugsymbols4_getscopeex.htm
old-project: debugger
ms.assetid: B91EF786-51F7-406E-BCC2-C917E6881886
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols4, IDebugSymbols4::GetScopeEx, GetScopeEx
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
req.alt-api: IDebugSymbols4.GetScopeEx
req.alt-loc: Dbgeng.h
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
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbols4::GetScopeEx method



## -description
Gets the scope as an extended frame structure. 



## -syntax

````
HRESULT GetScopeEx(
  [out, optional] PULONG64                                   InstructionOffset,
  [out, optional] PDEBUG_STACK_FRAME_EX                      ScopeFrame,
  [out]           _writes_bytes_opt_(ScopeContextSize) PVOID ScopeContext,
  [in]            ULONG                                      ScopeContextSize
);
````


## -parameters

### -param InstructionOffset [out, optional]

The offset of the instruction for the scope. 


### -param ScopeFrame [out, optional]

The scope frame returned as a <a href="..\dbgeng\ns-dbgeng-_debug_stack_frame_ex.md">DEBUG_STACK_FRAME_EX</a> structure. 


### -param ScopeContext [out]

A pointer to the scope context returned. 


### -param ScopeContextSize [in]

The size of the scope context.


## -returns
If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\dbgeng\ns-dbgeng-_debug_stack_frame_ex.md">DEBUG_STACK_FRAME_EX</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols4.md">IDebugSymbols4</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols4::GetScopeEx method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

