---
UID: NF:xpsrassvc.IXpsRasterizationFactory2.CreateRasterizer
title: IXpsRasterizationFactory2::CreateRasterizer method
author: windows-driver-content
description: The CreateRasterizer method creates an XPS rasterizer object that can convert content from XPS to PWG Raster using the XPS Rasterization Service. PWG Raster supports non-square DPIs.
old-location: print\ixpsrasterizationfactory2_createrasterizer.htm
old-project: print
ms.assetid: C31681A0-17C6-4255-9068-7486A2101AB7
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.ixpsrasterizationfactory2_createrasterizer, IXpsRasterizationFactory2 interface [Print Devices], CreateRasterizer method, CreateRasterizer method [Print Devices], IXpsRasterizationFactory2 interface, xpsrassvc/IXpsRasterizationFactory2::CreateRasterizer, CreateRasterizer, IXpsRasterizationFactory2::CreateRasterizer, IXpsRasterizationFactory2, CreateRasterizer method [Print Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: xpsrassvc.h
req.include-header: Xpsrassvc.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
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
req.lib: xpsrassvc.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	xpsrassvc.h
apiname:
-	IXpsRasterizationFactory2.CreateRasterizer
product: Windows
targetos: Windows
req.typenames: XPSRAS_BACKGROUND_COLOR
req.product: Windows 10 or later.
---


# CreateRasterizer method
The <b>CreateRasterizer</b> method creates an XPS rasterizer object that can convert content from XPS to PWG Raster using the <a href="https://msdn.microsoft.com/a0493b5f-d6f7-4f69-9c6e-e112c29250c9">XPS Rasterization Service</a>. PWG Raster supports non-square DPIs.

## Syntax

````
HRESULT CreateRasterizer(
  [in, optional]  IXpsOMPage              *xpsPage,
  [in]            FLOAT                   dpiX,
  [in]            FLOAT                   dpiY,
  [in]            XPSRAS_RENDERING_MODE   nonTextRenderingMode,
  [in]            XPSRAS_RENDERING_MODE   textRenderingMode,
  [in]            XPSRAS_PIXEL_FORMAT     pixelFormat,
  [in]            XPSRAS_BACKGROUND_COLOR backgroundColor,
  [out, optional] IXpsRasterizer          **ppIXpsRasterizer
);
````

## Parameters

`xpsPage`



`DPIX`



`DPIY`



`nonTextRenderingMode`

Rendering mode for nontext items in the rasterized output. This parameter indicates whether to generate antialiased output. Set this parameter to one of the following <a href="..\xpsrassvc\ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0001_0001.md">XPSRAS_RENDERING_MODE</a> enumeration values:

<ul>
<li>
XPSRAS_RENDERING_MODE_ANTIALIASED

</li>
<li>
XPSRAS_RENDERING_MODE_ALIASED

</li>
</ul>

`textRenderingMode`

Rendering mode for text in the rasterized output. This parameter indicates whether to generate antialiased output. Set this parameter to one of the following XPSRAS_RENDERING_MODE enumeration values:

<ul>
<li>
XPSRAS_RENDERING_MODE_ANTIALIASED

</li>
<li>
XPSRAS_RENDERING_MODE_ALIASED

</li>
</ul>

`pixelFormat`

Allows a caller to select the pixel format used by the IWICBitmap returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff556365">IXpsRasterizer::RasterizeRect</a>. Set this parameter to one of the following <a href="..\xpsrassvc\ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0003_0001.md">XPSRAS_PIXEL_FORMAT</a> enumeration values:

<ul>
<li>
XPSRAS_PIXEL_FORMAT_32BPP_PBGRA_UINT_SRGB

</li>
<li>
XPSRAS_PIXEL_FORMAT_64BPP_PRGBA_HALF_SCRGB

</li>
<li>
XPSRAS_PIXEL_FORMAT_128BPP_PRGBA_FLOAT_SCRGB

</li>
</ul>

`backgroundColor`

Allows a caller to select background color. Set this parameter to one of the following <a href="..\xpsrassvc\ne-xpsrassvc-__midl___midl_itf_xpsrassvc_0000_0004_0001.md">XPSRAS_BACKGROUND_COLOR</a> enumeration values:

<ul>
<li>
XPSRAS_BACKGROUND_COLOR_TRANSPARENT

</li>
<li>
XPSRAS_BACKGROUND_COLOR_OPAQUE

</li>
</ul>
The default background color is XPSRAS_BACKGROUND_COLOR_TRANSPARENT.

`ppIXpsRasterizer`




## Return Value

If this method succeeds, it returns <b>S_OK</b>. Otherwise, it returns an <b>HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Desktop |
| **Header** | xpsrassvc.h (include Xpsrassvc.h) |
| **Library** | xpsrassvc.h |

## See Also

<a href="..\xpsrassvc\nn-xpsrassvc-ixpsrasterizationfactory2.md">IXpsRasterizationFactory2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IXpsRasterizationFactory2::CreateRasterizer method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>