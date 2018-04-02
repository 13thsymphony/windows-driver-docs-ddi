---
UID: NF:printoem.OEMUpdateExternalFonts
title: OEMUpdateExternalFonts function
author: windows-driver-content
description: OEMUpdateExternalFonts function
old-location: print\oemupdateexternalfonts.htm
old-project: print
ms.assetid: 04b0a34f-0aec-4f42-8a2e-a29168a699e3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMUpdateExternalFonts, OEMUpdateExternalFonts function [Print Devices], print.oemupdateexternalfonts, print_obsoletefunctions_f42779e4-8a2d-45eb-801c-67e7e69cb96a.xml, printoem/OEMUpdateExternalFonts
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
-	OEMUpdateExternalFonts
product:
- Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMUpdateExternalFonts function


## Syntax

```
BOOL OEMUpdateExternalFonts(
  HANDLE hPrinter,
  HANDLE hHeap,
  PWSTR  pwstrCartridges
);
```

## Parameters

`hPrinter`



`hHeap`



`pwstrCartridges`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |