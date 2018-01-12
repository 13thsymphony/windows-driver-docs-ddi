---
UID: NF:printoem.OEMStretchBlt
title: OEMStretchBlt function
author: windows-driver-content
description: The OEMStretchBlt function provides stretching bit-block transfer capabilities between any combination of device-managed and GDI-managed surfaces.
old-location: print\oemstretchblt.htm
old-project: print
ms.assetid: 5a533a68-6bdb-45dc-b5d3-04fa8d3e7129
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: OEMStretchBlt
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
req.alt-api: OEMStretchBlt
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

# OEMStretchBlt function



## -description
The <code>OEMStretchBlt</code> function provides stretching bit-block transfer capabilities between any combination of device-managed and GDI-managed surfaces. 



## -syntax

````
BOOL APIENTRY OEMStretchBlt(
   SURFOBJ         *psoDest,
   SURFOBJ         *psoSrc,
   SURFOBJ         *psoMask,
   CLIPOBJ         *pco,
   XLATEOBJ        *pxlo,
   COLORADJUSTMENT *pca,
   POINTL          *pptlHTOrg,
   RECTL           *prclDest,
   RECTL           *prclSrc,
   POINTL          *pptlMask,
   ULONG           iMode
);
````


## -parameters

### -param psoDest 


### -param psoSrc 


### -param psoMask 


### -param pco 


### -param pxlo 


### -param pca 


### -param pptlHTOrg 


### -param prclDest 


### -param prclSrc 


### -param pptlMask 


### -param iMode 


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