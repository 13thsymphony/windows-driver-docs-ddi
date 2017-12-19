---
UID: NF.prcomoem.IPrintOemUni.ImageProcessing
title: IPrintOemUni::ImageProcessing method
author: windows-driver-content
description: The IPrintOemUni::ImageProcessing method can be used with Unidrv-supported printers to modify image bitmap data, in order to perform color formatting or halftoning.
old-location: print\iprintoemuni_imageprocessing.htm
old-project: print
ms.assetid: 201450cb-cda6-4dd3-93ee-056d1627b00d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrintOemUni, IPrintOemUni::ImageProcessing, ImageProcessing
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
req.alt-api: IPrintOemUni.ImageProcessing
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

# IPrintOemUni::ImageProcessing method



## -description
The <code>IPrintOemUni::ImageProcessing</code> method can be used with Unidrv-supported printers to modify image bitmap data, in order to perform color formatting or halftoning. The method can return the modified bitmap to Unidrv or send it directly to the print spooler.



## -syntax

````
HRESULT ImageProcessing(
        PDEVOBJ           pdevobj,
        PBYTE             pSrcBitmap,
        PBITMAPINFOHEADER pBitmapInfoHeader,
        PBYTE             pColorTable,
        DWORD             dwCallbackID,
        PIPPARAMS         pIPParams,
  [out] PBYTE             *ppbResult
);
````


## -parameters

### -param pdevobj 

Caller-supplied pointer to a <a href="print.devobj">DEVOBJ</a> structure.


### -param pSrcBitmap 

Caller-supplied pointer to an input <a href="wdkgloss.d#wdkgloss.device-independent_bitmap__dib_#wdkgloss.device-independent_bitmap__dib_"><i>DIB</i></a>.


### -param pBitmapInfoHeader 

Caller-supplied pointer to a BITMAPINFOHEADER structure that describes the bitmap pointed to by <i>pSrcBitmap</i>. The BITMAPINFOHEADER structure is described in the Microsoft Windows SDK documentation.


### -param pColorTable 

Caller-supplied pointer to a color table. This parameter is used only if the output format is eight bits per pixel. For more information, see the following Remarks section.

When interpreting a bitmap, you must examine the color table. Unidrv can modify the colors in a bitmap, but it will also make corresponding adjustments in the color table, resulting in no net change. However, if you ignore color table changes, and examine only the bitmap, an image might not print properly. For an example, see the discussion of the <i>pPaletteEntry</i> parameter in <a href="display.ht_get8bppmaskpalette">HT_Get8BPPMaskPalette</a>.


### -param dwCallbackID 

Caller-supplied value assigned to the *<b>IPCallbackID</b> attribute of the currently selected option for the ColorMode feature. For more information, see the following Remarks section.


### -param pIPParams 

Caller-supplied pointer to an <a href="..\printoem\ns-printoem-ipparams.md">IPPARAMS</a> structure.


### -param ppbResult [out]

Pointer to a memory location that contains the address of a buffer. The contents of the buffer depend on where the converted DIB should be sent.

If this method intends to send the converted DIB back to Unidrv and is successful in the conversion, it should set *<i>ppbResult</i> to the address of the buffer containing the converted DIB, and should return S_OK. If the conversion fails, the method should set *<i>ppbResult</i> to <b>NULL</b>, and should return E_FAIL.

If this method intends to send the converted DIB to the spooler and is successful in the conversion, the method should set *<i>ppbResult</i>  to <b>TRUE</b>, and should return S_OK. If the conversion fails, the method should set *<i>ppbResult</i> to <b>FALSE</b> and should return E_FAIL. For more information, see the discussion of the *<b>DevBPP</b> and *<b>DevNumOfPlanes</b> attributes in the Remarks section.


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
The <code>IPrintOemUni::ImageProcessing</code> method is used to modify image bitmaps before they are sent to the print spooler. Its purpose is to provide customized support for color modes and halftoning methods not supported by Unidrv. A printer driver that sends a bitmap to the print spooler (as opposed to sending it back to Unidrv) must set the *DevBPP and *DevNumOfPlanes attributes to zero in the printer's <a href="wdkgloss.g#wdkgloss.generic_printer_description__gpd_#wdkgloss.generic_printer_description__gpd_"><i>GPD</i></a> file.

If the method is implemented, and if the GPD file entry for the current color format contains an *<b>IPCallbackID</b> attribute, Unidrv calls the method each time a bitmap is available. The call is made after GDI renders the bitmap, which is then sent to the spooler. (For information about the *<b>IPCallbackID</b> attribute, see <a href="https://msdn.microsoft.com/e6f68a50-f044-406e-b92c-8449d126bceb">Option Attributes for the ColorMode Feature</a>.)

If the current color mode, as specified by <i>dwCallbackID</i>, is one that Unidrv supports, then the <code>IPrintOemUni::ImageProcessing</code> method should perform halftoning operations on the received bitmap and return it to Unidrv for spooling. If the current color mode is one that Unidrv does not support, the method must perform halftoning operations and then spool the bitmap.

If the method is performing only halftoning operations, it must do the following:

Perform halftoning operations on the data, as indicated by the <b>pHalftoneOption</b> member of the <a href="..\printoem\ns-printoem-ipparams.md">IPPARAMS</a> structure.

Return the modified image data to Unidrv by placing it in a buffer and supplying the buffer's address as the method's return value. The returned buffer can be the one pointed to by <i>pSrcBitmap</i>, or it can be one that is locally allocated.

For more information about customizing halftoning operations in Unidrv, see <a href="https://msdn.microsoft.com/cc14ff92-743b-42ca-b70f-0df768762f01">Customized Halftoning</a>.

To handle customized color formatting, the <code>IPrintOemUni::ImageProcessing</code> method must do the following:

Convert DIB data, described by the <i>pSrcBitmap</i> and <i>pBitmapInfoHeader</i> parameter values, into the color format indicated by <i>dwCallbackID</i>.

Send the data to the print spooler by calling the <a href="print.iprintoemdriveruni_drvwritespoolbuf">IPrintOemDriverUni::DrvWriteSpoolBuf</a> method.

Modify the printer's cursor position by making appropriate calls to the <a href="print.iprintoemdriveruni_drvxmoveto">IPrintOemDriverUni::DrvXMoveTo</a> and <a href="print.iprintoemdriveruni_drvymoveto">IPrintOemDriverUni::DrvYMoveTo</a> methods.

For more information about customizing color formatting operations in Unidrv, see <a href="https://msdn.microsoft.com/309d33e8-6338-4c32-8e03-d6cbf3371e16">Customized Color Formats</a>.

The <i>dwCallbackID</i> parameter indicates the type of color formatting, if any, that should be performed. Within the printer's GPD file, each *Option entry for the ColorMode feature describes a color format. If the format requires processing by the <code>IPrintOemUni::ImageProcessing</code> method, its *Option entry must contain an *<b>IPCallbackID</b> attribute. When Unidrv calls the <code>IPrintOemUni::ImageProcessing</code> method, it supplies the attribute value associated with the currently selected option for the ColorMode feature. This value is the <i>dwCallbackID</i> parameter's value.

Whether the <code>IPrintOemUni::ImageProcessing</code> method is performing color formatting operations and spooling image data, or just performing halftoning operations and returning processed bitmaps to Unidrv, it should export an <a href="print.iprintoemuni_memoryusage">IPrintOemUni::MemoryUsage</a> method if it allocates significant amounts of memory for destination bitmaps or other purposes. Otherwise, system performance might be degraded.

If the method is implemented, it is called for every raster region on the page. However, if a region is blank, the <b>bBlankBand</b> member of the <a href="..\printoem\ns-printoem-ipparams.md">IPPARAMS</a> structure is set to <b>TRUE</b>, which indicates the block is blank and the data is invalid. Because a band can be broken up into alternating blocks of blank and nonblank regions to optimize performance, the block size does not always correspond to the band size.

The source bitmap described by <i>pSrcBitmap</i> and <i>pBitmapInfoHeader</i> has the following characteristics:

DIB contents are top-down ordered and uncompressed.

The data format is one that is listed in <a href="https://msdn.microsoft.com/4d0faba6-1994-474f-a5d3-e25cd2800cf7">Handling Color Formats</a>.

If the format requires a color table, the table is pointed to by <i>pColorTable</i>.

Color data is in PRIMARY_ORDER_CBA format, as explained in the description of the <b>ulPrimaryOrder</b> member of the <a href="display.gdiinfo">GDIINFO</a> structure. In other words, if the color format is RGB or CMY, the least significant <i>n</i> bits must contain the blue or yellow value, the next <i>n</i> bits must contain the green or magenta value, and the next <i>n</i> bits must contain the red or cyan value. Unused bits are in the most significant position. If the format uses 4 bits per pixel, then <i>n</i> is 1. For 24 bits per pixel, <i>n</i> is 8, as shown in the following figure. For CYMK, the fourth group of <i>n</i> bits contains black.

The preceding figure depicts color data in PRIMARY_ORDER_CBA format for two pixels, with 24 bits of color data per pixel. Moving from low memory addresses to high memory addresses, there are eight bits of blue data, then eight bits of green data, and then eight bits of red data, after which the pattern repeats. This is also known as BGR device output order. 

For halftoning operations, in which a processed bitmap is returned to Unidrv, the returned bitmap must have the following characteristics:

DIB contents must be top-down ordered and uncompressed.

The data format must be one that is listed in <a href="https://msdn.microsoft.com/4d0faba6-1994-474f-a5d3-e25cd2800cf7">Handling Color Formats</a>, and it must be compatible with the *<b>DevBPP</b> and *<b>DevNumOfPlanes</b> attributes of the color format identified by <i>dwCallbackID</i>. (For information about these attributes, see <a href="https://msdn.microsoft.com/e6f68a50-f044-406e-b92c-8449d126bceb">Option Attributes for the ColorMode Feature</a>.)

If the format requires a color table, the table must be created and its address must be returned in <i>pColorTable</i>.

Color data must be returned in PRIMARY_ORDER_CBA format, as described for the source bitmap.

The BITMAPINFOHEADER structure specified by <i>pBitmapInfoHeader</i> must describe both the input and output bitmaps. The <code>IPrintOemUni::ImageProcessing</code> method must not change the structure's contents.

The <code>IPrintOemUni::ImageProcessing</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="print.iprintoemuni_getimplementedmethod">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "ImageProcessing" as input.


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

## -see-also
<dl>
<dt>
<a href="print.iprintoemuni_filtergraphics">IPrintOemUni::FilterGraphics</a>
</dt>
<dt>
<a href="display.ht_get8bppmaskpalette">HT_Get8BPPMaskPalette</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUni::ImageProcessing method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

