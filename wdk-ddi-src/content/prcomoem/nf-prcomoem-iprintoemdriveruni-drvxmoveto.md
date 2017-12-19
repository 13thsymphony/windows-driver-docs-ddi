---
UID: NF.prcomoem.IPrintOemDriverUni.DrvXMoveTo
title: IPrintOemDriverUni::DrvXMoveTo method
author: windows-driver-content
description: The IPrintOemDriverUni::DrvXMoveTo method is provided by the Unidrv driver so that a rendering plug-in can notify the driver of cursor x-position changes.
old-location: print\iprintoemdriveruni_drvxmoveto.htm
old-project: print
ms.assetid: 1f2c65ec-6218-438e-a853-4780f091a330
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrintOemDriverUni, IPrintOemDriverUni::DrvXMoveTo, DrvXMoveTo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintOemDriverUni.DrvXMoveTo
req.alt-loc: prcomoem.h
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

# IPrintOemDriverUni::DrvXMoveTo method



## -description
The <code>IPrintOemDriverUni::DrvXMoveTo</code> method is provided by the Unidrv driver so that a <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-in</a> can notify the driver of cursor x-position changes.



## -syntax

````
HRESULT DrvXMoveTo(
        PDEVOBJ pdevobj,
        INT     x,
        DWORD   dwFlags,
  [out] INT     *piResult
);
````


## -parameters

### -param pdevobj 

Caller-supplied pointer to a <a href="print.devobj">DEVOBJ</a> structure.


### -param x 

Caller-supplied value representing the number of units the cursor should be moved. The unit is defined by the MV_GRAPHICS flags in <i>dwFlags</i>.


### -param dwFlags 

One or more of the following caller-supplied bit flags:

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
MV_GRAPHICS

</td>
<td>
If set, the <i>x</i> parameter's value is expressed in dots, based on the printer's current resolution. For example, if the x resolution is 150 DPI and <i>x</i> is 75, the movement is ?? inch.

If not set, the <i>x</i> parameter's value is expressed in master units. For example, if the x master unit is 600 and <i>x</i> is 300, the movement is ?? inch.

</td>
</tr>
<tr>
<td>
MV_PHYSICAL

</td>
<td>
If set, the <i>x</i> parameter's value is relative to the cursor origin.

If not set, the <i>x</i> parameter's value is relative to the printable area's origin.

Cannot be set if MV_RELATIVE is set.

</td>
</tr>
<tr>
<td>
MV_RELATIVE

</td>
<td>
If set, specifies that the cursor should be moved <i>x</i> units from its current position.

If not set, specifies that the cursor should be moved <i>x</i> units from its origin.

</td>
</tr>
<tr>
<td>
MV_UPDATE

</td>
<td>
If set, specifies that Unidrv should update its current calculation of the cursor position without actually moving the cursor. (Should be set if <a href="print.iprintoemuni_imageprocessing">IPrintOemUni::ImageProcessing</a> has moved the cursor.)

If not set, specifies that Unidrv should update its current calculation of the cursor position and also move the cursor.

</td>
</tr>
</table>
 


### -param piResult [out]

Receives the method-supplied result of subtracting the actual new cursor position from the requested new cursor position. This value might be zero, but it is always nonnegative.


## -returns
The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not implemented.

 


## -remarks
The <code>IPrintOemDriverUni::DrvXMoveTo</code> and <a href="print.iprintoemdriveruni_drvymoveto">IPrintOemDriverUni::DrvYMoveTo</a> methods allow a rendering plug-in to send image data to the printer spooler without causing the printer driver to lose track of the printer's cursor position. If you provide an <a href="print.iprintoemuni_imageprocessing">IPrintOemUni::ImageProcessing</a> method that sends image data directly to the print spooler instead of returning it to the printer driver, the method should call <code>IPrintOemDriverUni::DrvXMoveTo</code> and <code>IPrintOemDriverUni::DrvYMoveTo</code>.

Either of two techniques can be used for updating the cursor position:

Whenever an <b>IPrintOemUni::ImageProcessing</b> method needs to update the cursor position, it can call <code>IPrintOemDriverUni::DrvXMoveTo</code> or <code>IPrintOemDriverUni::DrvYMoveTo</code> with the MV_UPDATE flag cleared. This causes Unidrv to send cursor commands to the print spooler and to update its internal calculation of the current cursor position.

The <b>IPrintOemUni::ImageProcessing</b> method can update the cursor by sending cursor commands directly to the print spooler. When the method has finished its spooling operation, it can call <code>IPrintOemDriverUni::DrvXMoveTo</code> or <code>IPrintOemDriverUni::DrvYMoveTo</code> with the MV_UPDATE flag set. This causes Unidrv to update its internal calculation of the current cursor position without sending cursor commands to the print spooler.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Prcomoem.h (include Prcomoem.h)</dt>
</dl>
</td>
</tr>
</table>