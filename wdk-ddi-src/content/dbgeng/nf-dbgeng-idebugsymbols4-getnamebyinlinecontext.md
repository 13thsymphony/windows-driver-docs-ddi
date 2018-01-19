---
UID : NF:dbgeng.IDebugSymbols4.GetNameByInlineContext
title : IDebugSymbols4::GetNameByInlineContext method
author : windows-driver-content
description : Gets a name by inline context.
old-location : debugger\idebugsymbols4_getnamebyinlinecontext.htm
old-project : debugger
ms.assetid : C87E70ED-FCB0-47B6-B6A3-A8EBC8E84058
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugSymbols4, IDebugSymbols4::GetNameByInlineContext, GetNameByInlineContext
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IDebugSymbols4.GetNameByInlineContext
req.alt-loc : Dbgeng.h
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


# GetNameByInlineContext method
Gets a name by inline context.

## Syntax

````
HRESULT GetNameByInlineContext(
  [in]            ULONG64                           Offset,
  [in]            ULONG                             InlineContext,
  [out]           _writes_opt_(NameBufferSize) PSTR NameBuffer,
  [in]            ULONG                             NameBufferSize,
  [out, optional] PULONG                            NameSize,
  [out, optional] PULONG64                          Displacement
);
````

## Parameters

`Offset`

An offset for the name.

`InlineContext`

The inline context.

`NameBuffer`

A pointer an output buffer.

`NameBufferSize`

The size of the name buffer.

`NameSize`

A pointer to the length of the name.

`Displacement`

A pointer to the displacement value of the name.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols4.md">IDebugSymbols4</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols4::GetNameByInlineContext method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>