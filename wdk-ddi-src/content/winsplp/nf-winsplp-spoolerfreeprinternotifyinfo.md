---
UID: NF:winsplp.SpoolerFreePrinterNotifyInfo
title: SpoolerFreePrinterNotifyInfo function
author: windows-driver-content
description: "."
old-location: print\spoolerfreeprinternotifyinfo.htm
old-project: print
ms.assetid: 5EA31AC4-FFAF-4AB8-B471-32B823F35D2F
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: SpoolerFreePrinterNotifyInfo function [Print Devices], winsplp/SpoolerFreePrinterNotifyInfo, SpoolerFreePrinterNotifyInfo, print.spoolerfreeprinternotifyinfo
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
-	SpoolerFreePrinterNotifyInfo
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---


# SpoolerFreePrinterNotifyInfo function


## Syntax

````
VOID WINAPI SpoolerFreePrinterNotifyInfo(
  _In_ PPRINTER_NOTIFY_INFO     pInfo
);
````

## Parameters

`pInfo`




## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | winsplp.h |
| **Library** | NtosKrnl.exe |