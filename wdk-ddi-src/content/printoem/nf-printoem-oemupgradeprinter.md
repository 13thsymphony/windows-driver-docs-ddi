---
UID: NF:printoem.OEMUpgradePrinter
title: OEMUpgradePrinter function
author: windows-driver-content
description: OEMUpgradePrinter function
old-location: print\oemupgradeprinter.htm
old-project: print
ms.assetid: 3f9ec3ca-a494-4a0a-87d8-1275b3b2a0b1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMUpgradePrinter, OEMUpgradePrinter function [Print Devices], print.oemupgradeprinter, print_obsoletefunctions_188db86f-1544-410e-ae88-c15c0e26cc3c.xml, printoem/OEMUpgradePrinter
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	printoem.h
api_name:
-	OEMUpgradePrinter
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
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
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |