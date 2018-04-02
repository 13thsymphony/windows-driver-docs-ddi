---
UID: NF:printoem.OEMTextOutAsBitmap
title: OEMTextOutAsBitmap function
author: windows-driver-content
description: OEMTextOutAsBitmap function
old-location: print\oemtextoutasbitmap.htm
old-project: print
ms.assetid: 37bf1cbe-9200-4d3e-b5e6-746f18293c1a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMTextOutAsBitmap, OEMTextOutAsBitmap function [Print Devices], print.oemtextoutasbitmap, print_obsoletefunctions_17993b3a-2343-4c6f-86ea-8273abaa8c80.xml, printoem/OEMTextOutAsBitmap
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
-	OEMTextOutAsBitmap
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMTextOutAsBitmap function


## Syntax

```
BOOL OEMTextOutAsBitmap(
  SURFOBJ  *pso,
  STROBJ   *pstro,
  FONTOBJ  *pfo,
  CLIPOBJ  *pco,
  RECTL    *prclExtra,
  RECTL    *prclOpaque,
  BRUSHOBJ *pboFore,
  BRUSHOBJ *pboOpaque,
  POINTL   *pptlOrg,
  MIX      mix
);
```

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