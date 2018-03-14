---
UID: NF:winsplp.SpoolerFindFirstPrinterChangeNotification
title: SpoolerFindFirstPrinterChangeNotification function
author: windows-driver-content
description: "."
old-location: print\spoolerfindfirstprinterchangenotification.htm
old-project: print
ms.assetid: 429A5DF5-46A6-4A41-A77B-4D5743C841DC
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: SpoolerFindFirstPrinterChangeNotification, SpoolerFindFirstPrinterChangeNotification function [Print Devices], print.spoolerfindfirstprinterchangenotification, winsplp/SpoolerFindFirstPrinterChangeNotification
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