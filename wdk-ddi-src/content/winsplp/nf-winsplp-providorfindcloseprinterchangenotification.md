---
UID: NF:winsplp.ProvidorFindClosePrinterChangeNotification
title: ProvidorFindClosePrinterChangeNotification function
author: windows-driver-content
description: "."
old-location: print\providorfindcloseprinterchangenotification.htm
old-project: print
ms.assetid: D7360F7B-394D-480A-B2AB-B4461B057E43
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ProvidorFindClosePrinterChangeNotification, ProvidorFindClosePrinterChangeNotification function [Print Devices], print.providorfindcloseprinterchangenotification, winsplp/ProvidorFindClosePrinterChangeNotification
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
-	ProvidorFindClosePrinterChangeNotification
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---


# ProvidorFindClosePrinterChangeNotification function


## Syntax

````
BOOL WINAPI ProvidorFindClosePrinterChangeNotification(
  _In_ HANDLE hPrinter
);
````

## Parameters

`hPrinter`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | winsplp.h |
| **Library** | NtosKrnl.exe |