---
UID: NF:dbgeng.IDebugSymbols3.CreateSymbolGroup2
title: IDebugSymbols3::CreateSymbolGroup2 method
author: windows-driver-content
description: The CreateSymbolGroup2 method creates a new symbol group.
old-location: debugger\createsymbolgroup2.htm
old-project: debugger
ms.assetid: 42ddf77a-14c8-4d6a-98a2-b0c67836990d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3::CreateSymbolGroup2, CreateSymbolGroup2
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
req.alt-api: IDebugSymbols3.CreateSymbolGroup2
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

# IDebugSymbols3::CreateSymbolGroup2 method



## -description
The <b>CreateSymbolGroup2</b>  method creates a new symbol group.



## -syntax

````
HRESULT CreateSymbolGroup2(
  [out] IDebugSymbolGroup **Group
);
````


## -parameters

### -param Group [out]

Receives an interface pointer for the new <a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a> object.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
The newly created symbol group is empty; it does not contain any <a href="debugger.symbols#symbols#symbols">symbols</a>.  Symbols may be added to the symbol group using <a href="https://msdn.microsoft.com/b77de459-b5ac-4752-89eb-f24fdde36134">IDebugSymbolGroup::AddSymbol</a>.

References to the returned object are managed like other COM objects, using the <b>IUnknown::AddRef</b> and <b>IUnknown::Release</b> methods.  In particular, the <b>IUnknown::Release</b> method must be called when the returned object is no longer needed.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff560088">Using Client Objects</a> for more information about using COM interfaces in the Debugger Engine API.

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b77de459-b5ac-4752-89eb-f24fdde36134">IDebugSymbolGroup::AddSymbol</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::CreateSymbolGroup2 method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

