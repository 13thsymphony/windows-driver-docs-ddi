---
UID : NF:printoem.OEMEndDoc
title : OEMEndDoc function
author : windows-driver-content
description : The OEMEndDoc function is called by the GDI when it has finished sending a document to the driver for rendering.
old-location : print\oemenddoc.htm
old-project : print
ms.assetid : 268a22ba-1dce-4326-bdf4-4d7e7e83257c
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : OEMEndDoc
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
req.alt-api : OEMEndDoc
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


# OEMEndDoc function
The <code>OEMEndDoc</code> function is called by the GDI when it has finished sending a document to the driver for rendering.

## Syntax

````
BOOL APIENTRY OEMEndDoc(
   SURFOBJ *pso,
   FLONG   fl
);
````

## Parameters

`pso`



`fl`




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