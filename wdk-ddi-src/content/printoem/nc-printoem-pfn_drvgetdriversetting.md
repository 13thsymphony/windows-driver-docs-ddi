---
UID: NC:printoem.PFN_DrvGetDriverSetting
title: PFN_DrvGetDriverSetting
author: windows-driver-content
description: The DrvGetDriverSetting function is obsolete.
old-location: print\drvgetdriversetting.htm
old-project: print
ms.assetid: 04473567-42ac-4d99-947d-6ec7b3bde90b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DrvGetDriverSetting, DrvGetDriverSetting callback function [Print Devices], PFN_DrvGetDriverSetting, print.drvgetdriversetting, print_obsoletefunctions_655cde75-fc70-4d6c-a7b4-8eb1e068ebd9.xml, printoem/DrvGetDriverSetting
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: printoem.h
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
-	UserDefined
api_location:
-	printoem.h
api_name:
-	DrvGetDriverSetting
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# PFN_DrvGetDriverSetting callback function
The <b>DrvGetDriverSetting</b> function is obsolete.

 Windows 2000 and later printer drivers should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553114">IPrintOemDriverUI::DrvGetDriverSetting</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff553036">IPrintCoreUI2::DrvGetDriverSetting</a> (UI plug-ins), <a href="https://msdn.microsoft.com/library/windows/hardware/ff553126">IPrintOemDriverUni::DrvGetDriverSetting</a> (Unidrv plug-ins) or <a href="https://msdn.microsoft.com/library/windows/hardware/ff553102">IPrintOemDriverPS::DrvGetDriverSetting</a> (Pscript plug-ins) 

This function pointer type defines the type of the <b>DrvGetDriverSetting</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559574">OEMUIPROCS</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff548571">DRVPROCS</a> structures.

## Syntax

```
PFN_DrvGetDriverSetting PfnDrvgetdriversetting;

BOOL PfnDrvgetdriversetting(
  PVOID pdriverobj,
  PCSTR Feature,
  PVOID pOutput,
  DWORD cbSize,
  PDWORD pcbNeeded,
  PDWORD pdwOptionsReturned
)
{...}
```

## Parameters

`pdriverobj`



`Feature`



`pOutput`



`cbSize`



`pcbNeeded`



`pdwOptionsReturned`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h |