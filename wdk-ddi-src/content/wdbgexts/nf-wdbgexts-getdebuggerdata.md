---
UID: NF:wdbgexts.GetDebuggerData
title: GetDebuggerData macro
author: windows-driver-content
description: The GetDebuggerData function retrieves information stored in a data block.
old-location: debugger\getdebuggerdata.htm
old-project: debugger
ms.assetid: a07afa2e-1f7d-4685-9ede-8b7805dd6583
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetDebuggerData, GetDebuggerData function [Windows Debugging], WdbgExts_Ref_a9b54b49-d8ac-4bee-a837-3986a250403a.xml, debugger.getdebuggerdata, wdbgexts/GetDebuggerData
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
req.target-type: Desktop
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
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	GetDebuggerData
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---


# GetDebuggerData function
The <b>GetDebuggerData</b> function retrieves information stored in a data block.

## Syntax

```
void GetDebuggerData(
   TAG,
   BUF,
   SIZE
);
```

## Parameters

`TAG`

TBD

`BUF`

TBD

`SIZE`

TBD


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |