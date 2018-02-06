---
UID: NF:winsplp.CreatePrinterIC
title: CreatePrinterIC function
author: windows-driver-content
description: "."
old-location: print\createprinteric.htm
old-project: print
ms.assetid: 87C99B3A-EF77-4D87-9953-BBE9628D2A3D
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: winsplp/CreatePrinterIC, CreatePrinterIC, print.createprinteric, CreatePrinterIC function [Print Devices]
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Winsplp.h
apiname:
-	CreatePrinterIC
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---


# CreatePrinterIC function


## Syntax

````
HANDLE WINAPI CreatePrinterIC(
  _In_     HANDLE     hPrinter,
  _In_opt_ LPDEVMODEW pDevMode
);
````

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
| **Library** | NtosKrnl.exe |