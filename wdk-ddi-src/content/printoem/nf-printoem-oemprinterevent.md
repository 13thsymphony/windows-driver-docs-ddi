---
UID: NF:printoem.OEMPrinterEvent
title: OEMPrinterEvent function
author: windows-driver-content
description: OEMPrinterEvent function
old-location: print\oemprinterevent.htm
old-project: print
ms.assetid: bbd37342-f0d0-43e0-bc27-1b47c426da6e
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: OEMPrinterEvent, OEMPrinterEvent function [Print Devices], printoem/OEMPrinterEvent, print.oemprinterevent, print_obsoletefunctions_0eaf5d52-f558-401d-a06f-80925e997e3a.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
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
-	printoem.h
apiname:
-	OEMPrinterEvent
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
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
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |