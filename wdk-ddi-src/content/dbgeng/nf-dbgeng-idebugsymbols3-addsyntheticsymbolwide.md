---
UID: NF:dbgeng.IDebugSymbols3.AddSyntheticSymbolWide
title: IDebugSymbols3::AddSyntheticSymbolWide method
author: windows-driver-content
description: The AddSyntheticSymbolWide method adds a synthetic symbol to a module in the current process.
old-location: debugger\addsyntheticsymbolwide.htm
old-project: debugger
ms.assetid: 06d4d1f1-8d28-46cc-8c80-8a67cf4ae4c3
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3::AddSyntheticSymbolWide, AddSyntheticSymbolWide
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
req.alt-api: IDebugSymbols3.AddSyntheticSymbolWide
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

# IDebugSymbols3::AddSyntheticSymbolWide method



## -description
The <b>AddSyntheticSymbolWide</b>  method adds a synthetic symbol to a module in the <a href="debugger.c#current_process#current_process"><i>current process</i></a>.



## -syntax

````
HRESULT AddSyntheticSymbolWide(
  [in]            ULONG64              Offset,
  [in]            ULONG                Size,
  [in]            PCSTR                Name,
  [in]            ULONG                Flags,
  [out, optional] PDEBUG_MODULE_AND_ID Id
);
````


## -parameters

### -param Offset [in]

Specifies the location in the process's virtual address space of the synthetic symbol.


### -param Size [in]

Specifies the size in bytes of the synthetic symbol.


### -param Name [in]

Specifies the name of the synthetic symbol.


### -param Flags [in]

Set to DEBUG_ADDSYNTHSYM_DEFAULT.


### -param Id [out, optional]

Receives the <a href="..\dbgeng\ns-dbgeng-_debug_module_and_id.md">DEBUG_MODULE_AND_ID</a> structure that identifies the synthetic symbol.  If <i>Id</i> is <b>NULL</b>, this information is not returned.


## -returns
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.

 

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.


## -remarks
The location of the synthetic symbol must not be the same as the location of another symbol.

If the module containing a synthetic symbol is reloaded - for example, by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554379">Reload</a> with the <i>Module</i> parameter set to the name of the module - the synthetic symbol will be discarded.

For more information about synthetic symbols, see <a href="debugger.using_symbols#synthetic_symbols#synthetic_symbols">Synthetic Symbols</a>.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554542">RemoveSyntheticSymbol</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537937">AddSyntheticModule</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::AddSyntheticSymbolWide method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

