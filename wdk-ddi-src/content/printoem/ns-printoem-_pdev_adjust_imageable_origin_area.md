---
UID: NS.PRINTOEM._PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA
title: _PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA
author: windows-driver-content
description: The PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA structure specifies the imageable origin area.
old-location: print\pdev_adjust_imageable_origin_area.htm
old-project: print
ms.assetid: 7b66ed24-64c2-49bc-a417-05fe11178b9f
ms.author: windowsdriverdev
ms.date: 12/9/2017
ms.keywords: _PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA, PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA, *PPDEV_ADJUST_IMAGEABLE_ORIGIN_AREA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA
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
req.product: Windows 10 or later.
---

# _PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA structure



## -description
The PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA structure specifies the imageable origin area.



## -syntax

````
typedef struct _PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA {
  POINT ptImageOrigin;
  SIZEL szlImageableArea;
} PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA, *PPDEV_ADJUST_IMAGEABLE_ORIGIN_AREA;
````


## -struct-fields

### -field ptImageOrigin

A POINT structure that specifies the origin of the imageable area, in graphics device units (pixels).


### -field szlImageableArea

A SIZEL structure that specifies the size of the image area, in graphics device units (pixels).


## -remarks
The PDEV_ADJUST_IMAGEABLE_ORIGIN_AREA structure is available in Windows Vista and later operating systems. 


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Printoem.h</dt>
</dl>
</td>
</tr>
</table>