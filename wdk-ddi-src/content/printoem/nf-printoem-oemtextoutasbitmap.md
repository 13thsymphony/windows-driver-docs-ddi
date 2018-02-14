---
UID: NF:printoem.OEMTextOutAsBitmap
title: OEMTextOutAsBitmap function
author: windows-driver-content
description: OEMTextOutAsBitmap function
old-location: print\oemtextoutasbitmap.htm
old-project: print
ms.assetid: 37bf1cbe-9200-4d3e-b5e6-746f18293c1a
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: printoem/OEMTextOutAsBitmap, OEMTextOutAsBitmap function [Print Devices], print_obsoletefunctions_17993b3a-2343-4c6f-86ea-8273abaa8c80.xml, OEMTextOutAsBitmap, print.oemtextoutasbitmap
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
-	OEMTextOutAsBitmap
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMTextOutAsBitmap function


## Syntax

````
BOOL APIENTRY OEMTextOutAsBitmap(
   SURFOBJ  *pso,
   STROBJ   *pstro,
   FONTOBJ  *pfo,
   CLIPOBJ  *pco,
   RECTL    *prclExtra,
   RECTL    *prclOpaque,
   BRUSHOBJ *pboFore,
   BRUSHOBJ *pboOpaque,
   POINTL   *pptlOrg,
   MIX      mix
);
````

## Parameters

`pso`



`pstro`



`pfo`



`pco`



`prclExtra`



`prclOpaque`



`pboFore`



`pboOpaque`



`pptlOrg`



`mix`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |
| **Library** | NtosKrnl.exe |