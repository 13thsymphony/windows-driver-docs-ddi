---
UID: NF:dbgeng.IDebugSymbols4.GetNameByInlineContextWide
title: IDebugSymbols4::GetNameByInlineContextWide method
author: windows-driver-content
description: Gets a name by inline context.
old-location: debugger\idebugsymbols4_getnamebyinlinecontextwide.htm
old-project: debugger
ms.assetid: D77F5755-75B0-48E6-BC5C-565022F884E1
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: dbgeng/IDebugSymbols4::GetNameByInlineContextWide, IDebugSymbols4 interface [Windows Debugging], GetNameByInlineContextWide method, IDebugSymbols4, GetNameByInlineContextWide, debugger.idebugsymbols4_getnamebyinlinecontextwide, GetNameByInlineContextWide method [Windows Debugging], GetNameByInlineContextWide method [Windows Debugging], IDebugSymbols4 interface, IDebugSymbols4::GetNameByInlineContextWide
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: dbgeng.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Dbgeng.h
apiname:
-	IDebugSymbols4.GetNameByInlineContextWide
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetNameByInlineContextWide method
Gets a name by inline context.

## Syntax

````
HRESULT GetNameByInlineContextWide(
  [in]            ULONG64                            Offset,
  [in]            ULONG                              InlineContext,
  [out]           _writes_opt_(NameBufferSize) PWSTR NameBuffer,
  [in]            ULONG                              NameBufferSize,
  [out, optional] PULONG                             NameSize,
  [out, optional] PULONG64                           Displacement
);
````

## Parameters

`Offset`

An offset for the inline context.

`InlineContext`

The inline context.

`NameBuffer`

A pointer an output buffer for a Unicode character string.

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
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols4.md">IDebugSymbols4</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols4::GetNameByInlineContextWide method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>