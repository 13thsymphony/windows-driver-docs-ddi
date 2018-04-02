---
UID: NF:winsplp.PlayGdiScriptOnPrinterIC
title: PlayGdiScriptOnPrinterIC function
author: windows-driver-content
description: "."
old-location: print\playgdiscriptonprinteric.htm
old-project: print
ms.assetid: DB5FCF40-77C2-4741-9E6B-77A9CD98E29A
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PlayGdiScriptOnPrinterIC, PlayGdiScriptOnPrinterIC function [Print Devices], print.playgdiscriptonprinteric, winsplp/PlayGdiScriptOnPrinterIC
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
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
-	HeaderDef
api_location:
-	Winsplp.h
api_name:
-	PlayGdiScriptOnPrinterIC
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---


# PlayGdiScriptOnPrinterIC function


## Syntax

```
BOOL PlayGdiScriptOnPrinterIC(
  HANDLE hPrinterIC,
  LPBYTE pIn,
  DWORD  cIn,
  LPBYTE pOut,
  DWORD  cOut,
  DWORD  ul
);
```

## Parameters

`hPrinterIC`



`pIn`



`cIn`



`pOut`



`cOut`



`ul`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | winsplp.h |