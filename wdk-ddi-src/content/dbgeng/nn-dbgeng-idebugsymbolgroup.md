---
UID: NN:dbgeng.IDebugSymbolGroup
title: IDebugSymbolGroup
author: windows-driver-content
description: IDebugSymbolGroup interface
old-location: debugger\idebugsymbolgroup.htm
old-project: debugger
ms.assetid: dd629e4a-938e-4db6-b0f3-6dd12a431486
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSystemObjects4, IDebugSystemObjects4::SetImplicitThreadDataOffset, SetImplicitThreadDataOffset
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDebugSymbolGroup
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugSymbolGroup interface



## -description

## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDebugSymbolGroup</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IDebugSymbolGroup</b> also has these types of members:

The <b>IDebugSymbolGroup</b> interface has these methods.

Adds a symbol to a symbol group.

Adds or removes the children of a symbol from a symbol group.

 Returns the number of symbols that are contained in a symbol group.


Returns the name of a symbol in a symbol group.


Returns the symbol parameters that describe the specified symbols in a symbol group.


Changes the type of a symbol in a symbol group. The symbol's entry is updated to represent the new type. 


Prints the specified symbols to the debugger console.

Removes the specified symbol from a symbol group.


 Removes the specified symbol from a symbol group.


Sets the value of the specified symbol.


 


## -members
The <b>IDebugSymbolGroup</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff537925">AddSymbol</a>
</td>
<td align="left" width="63%">
Adds a symbol to a symbol group.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543271">ExpandSymbol</a>
</td>
<td align="left" width="63%">
Adds or removes the children of a symbol from a symbol group.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>
</td>
<td align="left" width="63%">
 Returns the number of symbols that are contained in a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549121">GetSymbolName</a>
</td>
<td align="left" width="63%">
Returns the name of a symbol in a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549146">GetSymbolParameters</a>
</td>
<td align="left" width="63%">
Returns the symbol parameters that describe the specified symbols in a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553191">OutputAsType</a>
</td>
<td align="left" width="63%">
Changes the type of a symbol in a symbol group. The symbol's entry is updated to represent the new type. 


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff553264">OutputSymbols</a>
</td>
<td align="left" width="63%">
Prints the specified symbols to the debugger console.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554510">RemoveSymbolByIndex</a>
</td>
<td align="left" width="63%">
Removes the specified symbol from a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554518">RemoveSymbolByName</a>
</td>
<td align="left" width="63%">
 Removes the specified symbol from a symbol group.


</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561457">WriteSymbol</a>
</td>
<td align="left" width="63%">
Sets the value of the specified symbol.


</td>
</tr>
</table>Adds a symbol to a symbol group.

Adds or removes the children of a symbol from a symbol group.

 Returns the number of symbols that are contained in a symbol group.


Returns the name of a symbol in a symbol group.


Returns the symbol parameters that describe the specified symbols in a symbol group.


Changes the type of a symbol in a symbol group. The symbol's entry is updated to represent the new type. 


Prints the specified symbols to the debugger console.

Removes the specified symbol from a symbol group.


 Removes the specified symbol from a symbol group.


Sets the value of the specified symbol.


 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

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
<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup interface%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

