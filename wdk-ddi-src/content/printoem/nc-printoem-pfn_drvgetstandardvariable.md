---
UID: NC:printoem.PFN_DrvGetStandardVariable
title: PFN_DrvGetStandardVariable
author: windows-driver-content
description: This DrvGetStandardVariable function is obsolete.
old-location: print\drvgetstandardvariable.htm
old-project: print
ms.assetid: 743d8e3c-3115-4c2d-b7f3-6f99ba684693
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: print.drvgetstandardvariable, DrvGetStandardVariable, DrvGetStandardVariable callback function [Print Devices], DrvGetStandardVariable, PFN_DrvGetStandardVariable, PFN_DrvGetStandardVariable, printoem/DrvGetStandardVariable, print_obsoletefunctions_143de6bb-bea1-4292-8ac4-e34c2610a8ab.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	printoem.h
apiname:
-	DrvGetStandardVariable
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# PFN_DrvGetStandardVariable callback function
This <b>DrvGetStandardVariable</b> function is obsolete. 

Windows 2000 and later printer drivers should use <a href="https://msdn.microsoft.com/library/windows/hardware/ff553129">IPrintOemDriverUni::DrvGetStandardVariable</a>. 

This function pointer prototype defines the type of the <b>BGetStandardVariable</b> member of the <a href="..\printoem\ns-printoem-_drvprocs.md">DRVPROCS</a> structure.

## Syntax

```
PFN_DrvGetStandardVariable PfnDrvgetstandardvariable;

BOOL PfnDrvgetstandardvariable(
  PDEVOBJ pdevobj,
  DWORD dwIndex,
  PVOID pBuffer,
  DWORD cbSize,
  PDWORD pcbNeeded
)
{...}
```

## Parameters

`pdevobj`



`dwIndex`



`pBuffer`



`cbSize`



`pcbNeeded`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h |