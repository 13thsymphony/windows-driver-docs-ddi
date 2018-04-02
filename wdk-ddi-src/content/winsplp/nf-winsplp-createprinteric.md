---
UID: NF:winsplp.CreatePrinterIC
title: CreatePrinterIC function
author: windows-driver-content
description: "."
old-location: print\createprinteric.htm
old-project: print
ms.assetid: 87C99B3A-EF77-4D87-9953-BBE9628D2A3D
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CreatePrinterIC, CreatePrinterIC function [Print Devices], print.createprinteric, winsplp/CreatePrinterIC
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
-	CreatePrinterIC
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---


# CreatePrinterIC function


## Syntax

```
HANDLE CreatePrinterIC(
  HANDLE     hPrinter,
  LPDEVMODEW pDevMode
);
```

## Parameters

`hPrinter`



`pDevMode`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | winsplp.h |