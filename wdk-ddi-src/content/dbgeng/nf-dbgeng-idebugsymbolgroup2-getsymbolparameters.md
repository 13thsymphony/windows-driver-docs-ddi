---
UID: NF:dbgeng.IDebugSymbolGroup2.GetSymbolParameters
title: IDebugSymbolGroup2::GetSymbolParameters method
author: windows-driver-content
description: The GetSymbolParameters method returns the symbol parameters that describe the specified symbols in a symbol group.
old-location: debugger\getsymbolparameters.htm
old-project: debugger
ms.assetid: e6390a7c-bbe1-47d7-9411-d710c4ab58a8
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbolGroup2, IDebugSymbolGroup2::GetSymbolParameters, GetSymbolParameters
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
req.alt-api: IDebugSymbolGroup.GetSymbolParameters,IDebugSymbolGroup2.GetSymbolParameters
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
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# IDebugSymbolGroup2::GetSymbolParameters method



## -description
The <b>GetSymbolParameters</b> method returns the symbol parameters that describe the specified <a href="debugger.symbols#symbols#symbols">symbols</a> in a symbol group.



## -syntax

````
HRESULT GetSymbolParameters(
  [in]  ULONG                    Start,
  [in]  ULONG                    Count,
  [out] PDEBUG_SYMBOL_PARAMETERS Params
);
````


## -parameters

### -param Start [in]

The index in the symbol group of the first symbol whose parameters you want.  The index of a symbol is an identification number. This number ranges from zero through the number of symbols in the symbol group minus one.


### -param Count [in]

The number of symbol parameters that you want.


### -param Params [out]

The symbol parameters.  This array must hold at least <i>Count</i> elements.  For a description of these parameters, see <a href="..\dbgeng\ns-dbgeng-_debug_symbol_parameters.md">DEBUG_SYMBOL_PARAMETERS</a>.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method can also return error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.


## -remarks
For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup.md">IDebugSymbolGroup</a>
</dt>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>
</dt>
<dt>
<a href="..\dbgeng\ns-dbgeng-_debug_symbol_parameters.md">DEBUG_SYMBOL_PARAMETERS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup::GetSymbolParameters method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

