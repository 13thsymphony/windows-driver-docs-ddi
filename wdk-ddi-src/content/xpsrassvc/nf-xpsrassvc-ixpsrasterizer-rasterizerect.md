---
UID: NF:xpsrassvc.IXpsRasterizer.RasterizeRect
title: IXpsRasterizer::RasterizeRect method
author: windows-driver-content
description: The RasterizeRect method rasterizes an axis-aligned, rectangular region of an XPS fixed page.
old-location: print\ixpsrasterizer_rasterizerect.htm
old-project: print
ms.assetid: abf8dfc7-7921-4e9c-a338-ec783a01fca7
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IXpsRasterizer, IXpsRasterizer::RasterizeRect, RasterizeRect
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: xpsrassvc.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IXpsRasterizer.RasterizeRect
req.alt-loc: xpsrassvc.h
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
req.typenames: XPSRAS_BACKGROUND_COLOR
req.product: Windows 10 or later.
---

# IXpsRasterizer::RasterizeRect method



## -description
The <code>RasterizeRect</code> method rasterizes an axis-aligned, rectangular region of an XPS fixed page.



## -syntax

````
HRESULT RasterizeRect(
  [in]            INT                                x,
  [in]            INT                                y,
  [in]            INT                                width,
  [in]            INT                                height,
  [in, optional]  IXpsRasterizerNotificationCallback *notificationCallback,
  [out, optional] IWICBitmap                         **bitmap
);
````


## -parameters

### -param x [in]

The x coordinate, in pixels, at the left edge of the output bitmap.


### -param y [in]

The y coordinate, in pixels, at the top edge of the output bitmap.


### -param width [in]

The width, in pixels, of the output bitmap.


### -param height [in]

The height, in pixels, of the output bitmap.


### -param notificationCallback [in, optional]

Pointer to the <a href="https://msdn.microsoft.com/7616b5c7-a21f-4db1-923b-ebf2a039b5ec">IXpsRasterizerNotificationCallback</a> interface of a notification object that is implemented by the caller. This parameter is optional and can be <b>NULL</b> if the caller does not require notification callbacks.


### -param bitmap [out, optional]

Pointer to a location into which the method writes a pointer to the <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ee719675.aspx">IWICBitmap</a> interface of the newly created bitmap object. If the method fails, it writes <b>NULL</b> to this location and returns an error code.


## -returns
<code>RasterizeRect</code> returns S_OK if the call was successful. Otherwise, the method returns an error code. Possible error return values include:
<dl>
<dt><b>E_POINTER</b></dt>
</dl>Parameter <i>bitmap</i> is <b>NULL</b>.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>Parameter <i>width</i> or <i>height</i> is less than or equal to 0.

 


## -remarks
This method is supported in Windows 7 and later. It is not supported in versions of the Windows operating system before Windows 7.

If successful, this method creates a Windows imaging component (WIC) bitmap object and passes to the caller a counted reference to the object's <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ee719675.aspx">IWICBitmap</a> interface. When the object is no longer needed, the caller is responsible for releasing the object by calling the <a href="http://go.microsoft.com/fwlink/p/?linkid=98433">Release</a> method on the object's <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ee719675.aspx">IWICBitmap</a> interface.

The WIC bitmap created by this method has a 32-bit pixel format that contains 8-bit red, green, and blue channels and uses the standard RGB (sRGB) color space. In addition, the format contains an 8-bit alpha component. The color components in each pixel value are pre-multiplied by the alpha component. The pixel format is specified by the GUID value <b>GUID_WICPixelFormat32bppPBGRA</b>, which is defined in the header file Wincodec.h. For more information about this format, see <a href="http://go.microsoft.com/fwlink/p/?linkid=133874">Native Pixel Formats Overview</a>.

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff556350">IXpsRasterizationFactory::CreateRasterizer</a> method's <i>DPI</i> parameter specifies the resolution, in dots per inch, at which the bitmap is to be rendered. As described in the <a href="https://msdn.microsoft.com/library/windows/hardware/gg463431">XPS specification</a><u>, </u>the width and height of a fixed page in an XPS document are specified in 1/96-inch units. To determine the dimensions (in pixels) of the bitmap required to represent the entire fixed page, multiply the width and height by <i>DPI</i>/96.

To accommodate printers that require a fixed page to be rasterized as a series of horizontal or vertical bands, parameters <i>x</i>, <i>y</i>, <i>width</i>, and <i>height</i> specify a rectangular region of the fixed page that is to be rasterized. All four parameter values are specified in pixels. Parameters <i>x</i> and <i>y</i> are the coordinates of the top, left corner of the rectangular region; they are specified as pixel displacements from the coordinate origin (0, 0). Parameters <i>width</i> and <i>height</i> are the dimensions of the rectangular region.

For example, if <i>w</i>XPS and <i>h</i>XPS are the width and height of an XPS fixed page in 1/96-inch units, <code>RasterizeRect</code> generates a bitmap representation of the bottom half of the fixed page if parameters <i>x</i>, <i>y</i>, <i>width</i>, and <i>height</i> are set to the following values:

If the <i>notificationCallback</i> parameter is non-<b>NULL</b>, the <code>RasterizeRect</code> method takes a counted reference to the notification object's <b>IXpsRasterizerNotificationCallback</b> interface. It does so by calling the <b>AddRef</b> method on the interface before making any calls to the <b>IXpsRasterizerNotificationCallback::Continue</b> method. Before <code>RasterizeRect</code> returns, it releases the notification object by calling the <b>Release</b> method on the <b>IXpsRasterizerNotificationCallback</b> interface.

As explained in the <a href="https://msdn.microsoft.com/library/windows/hardware/gg463431">XPS specification</a><u>,</u> the optional <b>BleedBox</b> attribute can specify a bleed box that extends outside the boundaries of a fixed page. To accommodate bleed boxes, the rectangle defined by the parameters <i>x</i>, <i>y</i>, <i>width</i>, and <i>height</i> can also extend beyond the boundaries of the fixed page. The method accepts any values, positive or negative, for <i>x</i> and <i>y</i>, and it accepts any positive, nonzero values for <i>width</i> and <i>height</i>. The rectangle specified by these parameters defines the clipping region for the rasterization operation. If the rectangle extends beyond the boundaries of the fixed page, the clipping region also extends beyond these boundaries.

If the method fails and <i>bitmap</i> is non-<b>NULL</b>, the method sets *<i>bitmap</i> = <b>NULL</b>.

For a code example that calls the <code>RasterizeRect</code> method, see the XPSRasFilter sample in the WDK. This sample is located in the Src\Print\Xpsrasfilter folder in your WDK installation.


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
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of the Windows operating system.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Xpsrassvc.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ee719675.aspx">IWICBitmap</a></dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556366">IXpsRasterizer::SetMinimalLineWidth</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/7616b5c7-a21f-4db1-923b-ebf2a039b5ec">IXpsRasterizerNotificationCallback</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556350">IXpsRasterizationFactory::CreateRasterizer</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IXpsRasterizer::RasterizeRect method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

