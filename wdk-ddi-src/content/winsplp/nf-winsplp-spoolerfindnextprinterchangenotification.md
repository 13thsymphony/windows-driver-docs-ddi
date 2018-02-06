---
UID: NF:winsplp.SpoolerFindNextPrinterChangeNotification
title: SpoolerFindNextPrinterChangeNotification function
author: windows-driver-content
description: "."
old-location: print\spoolerfindnextprinterchangenotification.htm
old-project: print
ms.assetid: FE69BD53-F463-480A-820B-4259D6F48BD0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: SpoolerFindNextPrinterChangeNotification, winsplp/SpoolerFindNextPrinterChangeNotification, SpoolerFindNextPrinterChangeNotification function [Print Devices], print.spoolerfindnextprinterchangenotification
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
-	SpoolerFindNextPrinterChangeNotification
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---


# SpoolerFindNextPrinterChangeNotification function


## Syntax

````
BOOL WINAPI SpoolerFindNextPrinterChangeNotification(
  _In_        HANDLE     hPrinter,
  _Out_       LPDWORD    pfdwChange,
  _In_opt_    LPVOID     pPrinterNotifyOptions,
  _Inout_opt_ LPVOID     *ppPrinterNotifyInfo
);
````

## Parameters

`hPrinter`



`pfdwChange`



`pPrinterNotifyOptions`



`ppPrinterNotifyInfo`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | winsplp.h |
| **Library** | NtosKrnl.exe |