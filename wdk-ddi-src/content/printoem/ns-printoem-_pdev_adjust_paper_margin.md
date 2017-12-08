---
UID: NS.PRINTOEM._PDEV_ADJUST_PAPER_MARGIN
title: _PDEV_ADJUST_PAPER_MARGIN
author: windows-driver-content
description: The PDEV_ADJUST_PAPER_MARGIN structure specifies the imageable printing area.
old-location: print\pdev_adjust_paper_margin.htm
old-project: print
ms.assetid: f44a0a42-1fa1-4dd2-bd9f-74b0d0ed823e
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: _PDEV_ADJUST_PAPER_MARGIN, PDEV_ADJUST_PAPER_MARGIN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: Prcomoem.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PDEV_ADJUST_PAPER_MARGIN
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

# _PDEV_ADJUST_PAPER_MARGIN structure



## -description
The PDEV_ADJUST_PAPER_MARGIN structure specifies the imageable printing area.


## -syntax

````
typedef struct _PDEV_ADJUST_PAPER_MARGIN {
  RECTL rcImageableArea;
} PDEV_ADJUST_PAPER_MARGIN;
````


## -struct-fields

### -field rcImageableArea

Is a <a href="display.rectl">RECTL</a> structure that specifies the rectangular region that can be printed in. This region is specified in units of 0.001 mm.

## -remarks
This structure is available in Windows XP and later. 

The <i>pBuf</i> parameter of the <a href="print.iprintoemps2_getpdevadjustment">IPrintOemPS2::GetPDEVAdjustment</a> method can point to a structure of this type.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Printoem.h (include Prcomoem.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.iprintoemps2_getpdevadjustment">IPrintOemPS2::GetPDEVAdjustment</a>
</dt>
<dt>
<a href="display.rectl">RECTL</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20PDEV_ADJUST_PAPER_MARGIN structure%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
