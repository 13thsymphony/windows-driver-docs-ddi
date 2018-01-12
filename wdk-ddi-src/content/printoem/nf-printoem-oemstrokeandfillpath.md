---
UID: NF:printoem.OEMStrokeAndFillPath
title: OEMStrokeAndFillPath function
author: windows-driver-content
description: The OEMStrokeAndFillPath function concurrently strokes and fills a path.
old-location: print\oemstrokeandfillpath.htm
old-project: print
ms.assetid: f8a2df5d-426f-4872-8d54-55895c4fe6e3
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: OEMStrokeAndFillPath
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
req.alt-api: OEMStrokeAndFillPath
req.alt-loc: printoem.h
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
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMStrokeAndFillPath function



## -description
The <code>OEMStrokeAndFillPath</code> function concurrently strokes and fills a path.



## -syntax

````
BOOL APIENTRY OEMStrokeAndFillPath(
   SURFOBJ   *pso,
   PATHOBJ   *ppo,
   CLIPOBJ   *pco,
   XFORMOBJ  *pxo,
   BRUSHOBJ  *pboStroke,
   LINEATTRS *plineattrs,
   BRUSHOBJ  *pboFill,
   POINTL    *pptlBrushOrg,
   MIX       mixFill,
   FLONG     flOptions
);
````


## -parameters

### -param pso 


### -param ppo 


### -param pco 


### -param pxo 


### -param pboStroke 


### -param plineattrs 


### -param pboFill 


### -param pptlBrushOrg 


### -param mixFill 


### -param flOptions 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Printoem.h (include Printoem.h)</dt>
</dl>
</td>
</tr>
</table>