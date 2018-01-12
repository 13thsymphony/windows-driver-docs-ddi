---
UID: NF:printoem.OEMTextOut
title: OEMTextOut function
author: windows-driver-content
description: The OEMTextOut function calls for the driver to render a set of glyphs at specified positions.
old-location: print\oemtextout.htm
old-project: print
ms.assetid: cecce6ae-9b26-4b5f-aad3-69630ea340a4
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: OEMTextOut
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
req.alt-api: OEMTextOut
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

# OEMTextOut function



## -description
The <code>OEMTextOut</code> function calls for the driver to render a set of glyphs at specified positions.



## -syntax

````
BOOL APIENTRY OEMTextOut(
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


## -parameters

### -param pso 


### -param pstro 


### -param pfo 


### -param pco 


### -param prclExtra 


### -param prclOpaque 


### -param pboFore 


### -param pboOpaque 


### -param pptlOrg 


### -param mix 


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