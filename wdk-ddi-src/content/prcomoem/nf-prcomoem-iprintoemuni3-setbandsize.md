---
UID: NF:prcomoem.IPrintOemUni3.SetBandSize
title: IPrintOemUni3::SetBandSize method
author: windows-driver-content
description: The IPrintOemUni3::SetBandSize method can be used with Unidrv-supported printers to specify the desired band size on the printed output.
old-location: print\iprintoemuni3_setbandsize.htm
old-project: print
ms.assetid: e75fdfa5-2b25-4d89-b3ef-40cb445f874f
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemUni3, IPrintOemUni3::SetBandSize, SetBandSize
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
req.alt-api: IPrintOemUni3.SetBandSize
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemUni3::SetBandSize method



## -description
The <code>IPrintOemUni3::SetBandSize</code> method can be used with Unidrv-supported printers to specify the desired band size on the printed output.



## -syntax

````
HRESULT SetBandSize(
  [in] PDEVOBJ pdevobj,
  [in] INT     iFormat,
  [in] DWORD   dwPageWidthBytes,
  [in] DWORD   dwPageHeight,
  [in] DWORD   dwMaxHeight,
  [in] PDWORD  pdwRequiredHeight
);
````


## -parameters

### -param pdevobj [in]

A caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param iFormat [in]

An integer value that specifies the format of the bitmap in terms of the number of bits of color information per pixel that are required. This parameter can be one of the following values.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param BMF_1BPP

</td>
<td width="60%">
Monochrome

</td>
</tr>
<tr>

### -param BMF_4BPP

</td>
<td width="60%">
4 bits per pixel

</td>
</tr>
<tr>

### -param BMF_8BPP

</td>
<td width="60%">
8 bits per pixel

</td>
</tr>
<tr>

### -param BMF_16BPP

</td>
<td width="60%">
16 bits per pixel

</td>
</tr>
<tr>

### -param BMF_24BPP

</td>
<td width="60%">
24 bits per pixel

</td>
</tr>
<tr>

### -param BMF_32BPP

</td>
<td width="60%">
32 bits per pixel

</td>
</tr>
<tr>

### -param BMF_4RLE

</td>
<td width="60%">
4 bits per pixel; run length encoded

</td>
</tr>
<tr>

### -param BMF_8RLE

</td>
<td width="60%">
8 bits per pixel; run length encoded

</td>
</tr>
</table>
 


### -param dwPageWidthBytes [in]

A Unidrv-supplied value that specifies the width of the printing area, in bytes.


### -param dwPageHeight [in]

A Unidrv-supplied value that specifies the height of the printing area, in pixels.


### -param dwMaxHeight [in]

A Unidrv-supplied value that specifies the maximum allowable height of the printing area, in pixels.


### -param pdwRequiredHeight [in]

A caller-supplied pointer to a DWORD that contains the height of the printing area, in pixels, required by the rendering plug-in.


## -returns
The method must return one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded. See Note.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed. See Note.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>Unidrv should compute the banding size.

 


## -remarks
This method is available in Windows Vista and later.

This method is used by a rendering plug-in to specify band size using the plug-in's own calculations, rather than using Unidrv's band size calculations.

You can disable banding operations by Unidrv by setting the <i>dwPageHeight</i> value to *<i>pdwRequiredHeight</i>, but you should consider the performance effect of the height value that the rendering plug-in requests. For rendering, Unidrv needs at least the amount of memory that is calculated by multiplying <i>dwPageWidthBytes</i> by *<i>pdwRequiredHeight</i>. If the rendering plug-in supports the <a href="https://msdn.microsoft.com/library/windows/hardware/ff554245">IPrintOemUni::DriverDMS</a> method and that method returns "S_OK", <code>IPrintOemUni3::SetBandSize</code> is not called.

If this method is defined and the printer's generic printer description (GPD) file indicates that preanalysis is disabled (the GPD file includes "*<b>PreAnalysisOptions</b>: 0"), Unidrv calls this method to calculate band size. For information about the <b>PreAnalysisOptions</b> attribute, see <a href="https://msdn.microsoft.com/4c07145a-9a08-4507-8bab-769617e73d77">Preanalysis Infrastructure</a>.

If the rendering plug-in supports <a href="https://msdn.microsoft.com/library/windows/hardware/ff554245">IPrintOemUni::DriverDMS</a> and that method returns S_OK, <code>IPrintOemUni3::SetBandSize</code> is not called.


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