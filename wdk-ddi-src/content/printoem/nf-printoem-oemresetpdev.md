---
UID: NF:printoem.OEMResetPDEV
title: OEMResetPDEV function
author: windows-driver-content
description: OEMResetPDEV function
old-location: print\oemresetpdev.htm
old-project: print
ms.assetid: 92ae8382-49f3-4bfc-917a-047991953809
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: print.oemresetpdev, OEMResetPDEV, print_obsoletefunctions_c49829da-bbf6-4438-b291-c8dd93856311.xml, OEMResetPDEV function [Print Devices], printoem/OEMResetPDEV
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
-	OEMResetPDEV
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMResetPDEV function


## Syntax

````
BOOL APIENTRY OEMResetPDEV(
   PDEVOBJ pdevobjOld,
   PDEVOBJ pdevobjNew
);
````

## Parameters

`pdevobjOld`



`pdevobjNew`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |