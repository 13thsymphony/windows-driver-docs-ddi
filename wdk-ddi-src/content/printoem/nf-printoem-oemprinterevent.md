---
UID : NF:printoem.OEMPrinterEvent
title : OEMPrinterEvent function
author : windows-driver-content
description : OEMPrinterEvent function
old-location : print\oemprinterevent.htm
old-project : print
ms.assetid : bbd37342-f0d0-43e0-bc27-1b47c426da6e
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : OEMPrinterEvent
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : printoem.h
req.include-header : Printoem.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : OEMPrinterEvent
req.alt-loc : printoem.h
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
req.typenames : STDVARIABLEINDEX
req.product : Windows 10 or later.
---


# OEMPrinterEvent function


## Syntax

````
BOOL APIENTRY OEMPrinterEvent(
   PWSTR  pPrinterName,
   INT    iDriverEvent,
   DWORD  dwFlags,
   LPARAM lParam
);
````

## Parameters

`pPrinterName`



`iDriverEvent`



`dwFlags`



`lParam`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | printoem.h (include Printoem.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |