---
UID: NF:printoem.OEMUpgradePrinter
title: OEMUpgradePrinter function
author: windows-driver-content
description: OEMUpgradePrinter function
old-location: print\oemupgradeprinter.htm
old-project: print
ms.assetid: 3f9ec3ca-a494-4a0a-87d8-1275b3b2a0b1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: print_obsoletefunctions_188db86f-1544-410e-ae88-c15c0e26cc3c.xml, print.oemupgradeprinter, OEMUpgradePrinter function [Print Devices], printoem/OEMUpgradePrinter, OEMUpgradePrinter
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
| **Library** | NtosKrnl.exe |