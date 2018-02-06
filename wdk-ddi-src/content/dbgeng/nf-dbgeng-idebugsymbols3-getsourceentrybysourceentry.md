---
UID: NF:dbgeng.IDebugSymbols3.GetSourceEntryBySourceEntry
title: IDebugSymbols3::GetSourceEntryBySourceEntry method
author: windows-driver-content
description: Allows navigation within the source entries.
old-location: debugger\idebugsymbols3_getsourceentrybysourceentry.htm
old-project: debugger
ms.assetid: 4ED5D2DC-8D31-458A-80F2-F681DC375769
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: GetSourceEntryBySourceEntry method [Windows Debugging], IDebugSymbols3 interface, GetSourceEntryBySourceEntry method [Windows Debugging], debugger.idebugsymbols3_getsourceentrybysourceentry, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetSourceEntryBySourceEntry method, GetSourceEntryBySourceEntry, IDebugSymbols3::GetSourceEntryBySourceEntry, dbgeng/IDebugSymbols3::GetSourceEntryBySourceEntry
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
-	IDebugSymbols3.GetSourceEntryBySourceEntry
product: Windows
targetos: Windows
req.typenames: "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetSourceEntryBySourceEntry method
Allows navigation within the
    source entries.

## Syntax

````
HRESULT GetSourceEntryBySourceEntry(
  [in]  PDEBUG_SYMBOL_SOURCE_ENTRY FromEntry,
  [in]  ULONG                      Flags,
  [out] PDEBUG_SYMBOL_SOURCE_ENTRY ToEntry
);
````

## Parameters

`FromEntry`

A pointer to a <a href="..\dbgeng\ns-dbgeng-_debug_symbol_source_entry.md">DEBUG_SYMBOL_SOURCE_ENTRY</a> as the input entry.

`Flags`

A bit-set that contains options that affect the behavior of this method.

`ToEntry`

A pointer to a <a href="..\dbgeng\ns-dbgeng-_debug_symbol_source_entry.md">DEBUG_SYMBOL_SOURCE_ENTRY</a> as the output entry.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>

<a href="..\dbgeng\ns-dbgeng-_debug_symbol_source_entry.md">DEBUG_SYMBOL_SOURCE_ENTRY</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetSourceEntryBySourceEntry method%20 RELEASE:%20(1/19/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>