---
UID : NF:printoem.OEMUpgradePrinter
title : OEMUpgradePrinter function
author : windows-driver-content
description : OEMUpgradePrinter function
old-location : print\oemupgradeprinter.htm
old-project : print
ms.assetid : 3f9ec3ca-a494-4a0a-87d8-1275b3b2a0b1
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : OEMUpgradePrinter
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
req.alt-api : OEMUpgradePrinter
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


# OEMUpgradePrinter function


## Syntax

````
BOOL APIENTRY OEMUpgradePrinter(
   DWORD dwLevel,
   PBYTE pDriverUpgradeInfo
);
````

## Parameters

`dwLevel`



`pDriverUpgradeInfo`




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