---
UID: NF:winsplp.ProvidorFindFirstPrinterChangeNotification
title: ProvidorFindFirstPrinterChangeNotification function
author: windows-driver-content
description: "."
old-location: print\providorfindfirstprinterchangenotification.htm
old-project: print
ms.assetid: AFDA244D-D692-44C1-8BA3-5E1F013558D6
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ProvidorFindFirstPrinterChangeNotification function [Print Devices], ProvidorFindFirstPrinterChangeNotification, print.providorfindfirstprinterchangenotification, winsplp/ProvidorFindFirstPrinterChangeNotification
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
-	ProvidorFindFirstPrinterChangeNotification
product: Windows
targetos: Windows
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---


# ProvidorFindFirstPrinterChangeNotification function


## Syntax

````
BOOL WINAPI ProvidorFindFirstPrinterChangeNotification(
  _In_      HANDLE                   hPrinter,
            DWORD                    fdwFlags,
            DWORD                    fdwOptions,
  _In_      HANDLE                   hNotify,
  _In_opt_  PVOID                    pPrinterNotifyOptions,
  _Out_opt_ PVOID                    pvReserved1
);
````

## Parameters

`hPrinter`



`fdwFlags`



`fdwOptions`



`hNotify`



`pPrinterNotifyOptions`



`pvReserved1`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | winsplp.h |
| **Library** | NtosKrnl.exe |