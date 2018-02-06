---
UID: NF:winsplp.SpoolerFindFirstPrinterChangeNotification
title: SpoolerFindFirstPrinterChangeNotification function
author: windows-driver-content
description: "."
old-location: print\spoolerfindfirstprinterchangenotification.htm
old-project: print
ms.assetid: 429A5DF5-46A6-4A41-A77B-4D5743C841DC
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: winsplp/SpoolerFindFirstPrinterChangeNotification, print.spoolerfindfirstprinterchangenotification, SpoolerFindFirstPrinterChangeNotification, SpoolerFindFirstPrinterChangeNotification function [Print Devices]
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
-	SpoolerFindFirstPrinterChangeNotification
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---


# SpoolerFindFirstPrinterChangeNotification function


## Syntax

````
BOOL WINAPI SpoolerFindFirstPrinterChangeNotification(
  _In_      HANDLE                   hPrinter,
            DWORD                    fdwFilterFlags,
            DWORD                    fdwOptions,
  _In_      PVOID                    pPrinterNotifyOptions,
  _In_opt_  PVOID                    pvReserved,
  _In_      PVOID                    pNotificationConfig,
  _Out_opt_ PHANDLE                  phNotify,
  _Out_opt_ PHANDLE                  phEvent
);
````

## Parameters

`hPrinter`



`fdwFilterFlags`



`fdwOptions`



`pPrinterNotifyOptions`



`pvReserved`



`pNotificationConfig`



`phNotify`



`phEvent`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | winsplp.h |
| **Library** | NtosKrnl.exe |