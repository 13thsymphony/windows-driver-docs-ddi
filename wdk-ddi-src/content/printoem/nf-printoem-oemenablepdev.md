---
UID: NF:printoem.OEMEnablePDEV
title: OEMEnablePDEV function
author: windows-driver-content
description: OEMEnablePDEV function
old-location: print\oemenablepdev.htm
old-project: print
ms.assetid: 0088f5f6-eb68-4081-8cca-3d34fd10593a
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: print.oemenablepdev, print_obsoletefunctions_f6d0b164-0458-442f-ac6a-791592883196.xml, OEMEnablePDEV function [Print Devices], OEMEnablePDEV, printoem/OEMEnablePDEV
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
-	OEMEnablePDEV
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMEnablePDEV function


## Syntax

````
PDEVOEM APIENTRY OEMEnablePDEV(
          PDEVOBJ                            pdevobj,
  _In_    PWSTR                              pPrinterName,
          ULONG                              cPatterns,
  _In_    _updates_(cPatterns) HSURF         *phsurfPatterns,
          ULONG                              cjGdiInfo,
  _Inout_ _updates_bytes_(cjGdiInfo) GDIINFO *pGdiInfo,
          ULONG                              cjDevInfo,
  _Inout_ _updates_bytes_(cjDevInfo) DEVINFO *pDevInfo,
  _In_    DRVENABLEDATA                      *pded
);
````

## Parameters

`pdevobj`



`pPrinterName`



`cPatterns`



`phsurfPatterns`



`cjGdiInfo`



`pGdiInfo`



`cjDevInfo`



`pDevInfo`



`pded`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |