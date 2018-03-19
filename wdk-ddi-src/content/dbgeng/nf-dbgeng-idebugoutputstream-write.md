---
UID: NF:dbgeng.IDebugOutputStream.Write
title: IDebugOutputStream::Write method
author: windows-driver-content
description: Writes to the debug output stream.
old-location: debugger\idebugoutputstream_write.htm
old-project: debugger
ms.assetid: CC609DA8-9778-4AFC-9205-5F68AF15927C
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IDebugOutputStream, IDebugOutputStream interface [Windows Debugging], Write method, IDebugOutputStream::Write, Write method [Windows Debugging], Write method [Windows Debugging], IDebugOutputStream interface, Write,IDebugOutputStream.Write, dbgeng/IDebugOutputStream::Write, debugger.idebugoutputstream_write
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugOutputStream.Write
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# Write method
Writes to the debug output stream.

## Syntax

````
HRESULT Write(
  [in] PCWSTR psz
);
````

## Parameters

`psz`

A pointer to a Unicode character string of content to write.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h |

## See Also

<a href="..\dbgeng\nn-dbgeng-idebugoutputstream.md">IDebugOutputStream</a>