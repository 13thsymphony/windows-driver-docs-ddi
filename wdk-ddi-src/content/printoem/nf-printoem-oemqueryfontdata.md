---
UID: NF:printoem.OEMQueryFontData
title: OEMQueryFontData function
author: windows-driver-content
description: The OEMQueryFontData function retrieves information about a realized font.
old-location: print\oemqueryfontdata.htm
old-project: print
ms.assetid: dccf1bca-6ea5-4cf0-b768-b569898c90e7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMQueryFontData, OEMQueryFontData function [Print Devices], print.oemqueryfontdata, print_unidrv-pscript_rendering_5044e745-e2bf-4047-a8d8-371fc21c33fa.xml, printoem/OEMQueryFontData
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
-	OEMQueryFontData
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMQueryFontData function
The <code>OEMQueryFontData</code> function retrieves information about a realized font.

## Syntax

```
LONG OEMQueryFontData(
  DHPDEV    dhpdev,
  FONTOBJ   *pfo,
  ULONG     iMode,
  HGLYPH    hg,
  GLYPHDATA *pgd,
  PVOID     pv,
  ULONG     cjSize
);
```

## Parameters

`dhpdev`



`pfo`



`iMode`



`hg`



`pgd`



`pv`



`cjSize`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |