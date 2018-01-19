---
UID : NF:winsplp.SpoolerFindFirstPrinterChangeNotification
title : SpoolerFindFirstPrinterChangeNotification function
author : windows-driver-content
description : .
old-location : print\spoolerfindfirstprinterchangenotification.htm
old-project : print
ms.assetid : 429A5DF5-46A6-4A41-A77B-4D5743C841DC
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : SpoolerFindFirstPrinterChangeNotification
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : winsplp.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : SpoolerFindFirstPrinterChangeNotification
req.alt-loc : Winsplp.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : NOTIFICATION_CONFIG_FLAGS
req.product : Windows 10 or later.
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
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | winsplp.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |