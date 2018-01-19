---
UID : NF:dbgeng.IDebugSymbolGroup2.GetSymbolSize
title : IDebugSymbolGroup2::GetSymbolSize method
author : windows-driver-content
description : The GetSymbolSize method returns the size of a symbol's value.
old-location : debugger\getsymbolsize.htm
old-project : debugger
ms.assetid : f35bbbeb-585b-47b0-ae36-bd37fe9e1bbc
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugSymbolGroup2, IDebugSymbolGroup2::GetSymbolSize, GetSymbolSize
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IDebugSymbolGroup2.GetSymbolSize
req.alt-loc : dbgeng.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetSymbolSize method
The <b>GetSymbolSize</b> method returns the size of a symbol's value.

## Syntax

````
HRESULT GetSymbolSize(
  [in]  ULONG  Index,
  [out] PULONG Size
);
````

## Parameters

`Index`

The index of the symbol to remove. The index of a symbol is an identification number. The index ranges from zero through the number of symbols in the symbol group minus one.

`Size`

The size, in bytes, of the symbol's value. This information might not be available. If this information is not available, <i>Size</i> is set to zero.  For some symbols (for example, a function's code), the data might be split over multiple regions. In this situation, <i>Size</i> is not meaningful.


## Return Value

<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>The symbol does not have type data associated with it.

 

This method can also return other error values.  For more information, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.

## Remarks

For more information about symbol groups, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554702">Scopes and Symbol Groups</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbolgroup2.md">IDebugSymbolGroup2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547975">GetNumberSymbols</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/b6f03eb5-e386-4e88-a729-db08f1fa460c">IDebugSymbols::GetTypeSize</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbolGroup2::GetSymbolSize method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>