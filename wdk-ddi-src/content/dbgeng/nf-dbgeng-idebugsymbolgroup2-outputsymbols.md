---
UID: NF:dbgeng.IDebugSymbolGroup2.OutputSymbols
title: IDebugSymbolGroup2::OutputSymbols method
author: windows-driver-content
description: The OutputSymbols method prints the specified symbols to the debugger console.
old-location: debugger\outputsymbols.htm
old-project: debugger
ms.assetid: 1fe99cc4-35d9-432a-aed9-074d40438976
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbolGroup2, IDebugSymbolGroup2::OutputSymbols, OutputSymbols
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
req.alt-api: IDebugSymbolGroup.OutputSymbols,IDebugSymbolGroup2.OutputSymbols
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

# IDebugSymbolGroup2::OutputSymbols method



## -description
The <b>OutputSymbols</b> method prints the specified <a href="debugger.symbols#symbols#symbols">symbols</a> to the debugger console.



## -syntax

````
HRESULT OutputSymbols(
  [in] ULONG OutputControl,
  [in] ULONG Flags,
  [in] ULONG Start,
  [in] ULONG Count
);
````


## -parameters

### -param OutputControl [in]

The output control to use when printing the symbols' information.  For more information about possible values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff541517">DEBUG_OUTCTL_XXX</a>.  For more information about output, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff550971">Input and Output</a>.


### -param Flags [in]

The flags that determine what information is printed for each symbol.  By default, the output includes the symbol's name, offset, value, and type.  The format for the output is as follows:

<code>Name**NAME**Offset**OFF**Value**VALUE**Type**TYPE**</code>

You can use the following bit flags to suppress the output of one of these pieces of information together with the corresponding marker.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
DEBUG_OUTPUT_SYMBOLS_NO_NAMES

</td>
<td>
Suppress output of the symbol's name.

</td>
</tr>
<tr>
<td>
DEBUG_OUTPUT_SYMBOLS_NO_OFFSETS

</td>
<td>
Suppress output of the symbol's offset.

</td>
</tr>
<tr>
<td>
DEBUG_OUTPUT_SYMBOLS_NO_VALUES

</td>
<td>
Suppress output of the symbol's value.

</td>
</tr>
<tr>
<td>
DEBUG_OUTPUT_SYMBOLS_NO_TYPES

</td>
<td>
Suppress output of the symbol's type.

</td>
</tr>
</table>
 


### -param Start [in]

The index of the first symbol in the symbol group to print.  The index of a symbol is an identification number. This number ranges from zero through the number of symbols in the symbol group minus one.


### -param Count [in]

The number of symbols to print.


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup::OutputSymbols method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

