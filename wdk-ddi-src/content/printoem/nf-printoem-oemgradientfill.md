---
UID: NF:printoem.OEMGradientFill
title: OEMGradientFill function
author: windows-driver-content
description: The OEMGradientFill function shades the specified primitives.
old-location: print\oemgradientfill.htm
old-project: print
ms.assetid: 8a25d44b-c83b-4454-858b-117dbb6cc4b7
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: OEMGradientFill function [Print Devices], OEMGradientFill, print.oemgradientfill, print_unidrv-pscript_rendering_ddb279ca-c526-4993-94ce-cf8caa0febb4.xml, printoem/OEMGradientFill
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
-	OEMGradientFill
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMGradientFill function
The <code>OEMGradientFill</code> function shades the specified primitives.

## Syntax

````
BOOL APIENTRY OEMGradientFill(
   SURFOBJ   *psoDest,
   CLIPOBJ   *pco,
   XLATEOBJ  *pxlo,
   TRIVERTEX *pVertex,
   ULONG     nVertex,
   PVOID     pMesh,
   ULONG     nMesh,
   RECTL     *prclExtents,
   POINTL    *pptlDitherOrg,
   ULONG     ulMode
);
````

## Parameters

`psoDest`



`pco`



`pxlo`



`pVertex`



`nVertex`



`pMesh`



`nMesh`



`prclExtents`



`pptlDitherOrg`



`ulMode`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |