---
UID : NF:printoem.OEMFillPath
title : OEMFillPath function
author : windows-driver-content
description : The OEMFillPath function handles the filling of closed paths.
old-location : print\oemfillpath.htm
old-project : print
ms.assetid : a61081ad-308e-49c5-a428-1142520d38e4
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : OEMFillPath
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
req.alt-api : OEMEscape
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


# OEMFillPath function
The <code>OEMFillPath</code> function handles the filling of closed paths.

## Syntax

````
BOOL APIENTRY OEMEscape(
   SURFOBJ  *pso,
   PATHOBJ  *ppo,
   CLIPOBJ  *pco,
   BRUSHOBJ *pbo,
   POINTL   *pptlBrushOrg,
   MIX      mix,
   FLONG    flOptions
);
````

## Parameters

`pso`



`ppo`



`pco`



`pbo`



`pptlBrushOrg`



`mix`



`flOptions`




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