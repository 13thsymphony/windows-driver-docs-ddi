---
UID: NF:prcomoem.IPrintOemUni.TTDownloadMethod
title: IPrintOemUni::TTDownloadMethod method
author: windows-driver-content
description: The IPrintOemUni::TTDownloadMethod method enables a rendering plug-in to indicate the format that Unidrv should use for a specified TrueType soft font.
old-location: print\iprintoemuni_ttdownloadmethod.htm
old-project: print
ms.assetid: bf8c2baf-eaca-4d0e-a6d6-dba67b2f85db
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemUni, IPrintOemUni::TTDownloadMethod, TTDownloadMethod
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
req.alt-api: IPrintOemUni.TTDownloadMethod
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

# IPrintOemUni::TTDownloadMethod method



## -description
The <code>IPrintOemUni::TTDownloadMethod</code> method enables a rendering plug-in to indicate the format that Unidrv should use for a specified TrueType soft font.



## -syntax

````
HRESULT TTDownloadMethod(
        PDEVOBJ     pdevobj,
        PUNIFONTOBJ pUFObj,
  [out] DWORD       *pdwResult
);
````


## -parameters

### -param pdevobj 

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param pUFObj 

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_unifontobj.md">UNIFONTOBJ</a> structure.


### -param pdwResult [out]

Receives one of the following method-supplied constant values:

<table>
<tr>
<th>Value</th>
<th>Definition</th>
</tr>
<tr>
<td>
TTDOWNLOAD_BITMAP

</td>
<td>
Unidrv should download the specified font as bitmaps.

</td>
</tr>
<tr>
<td>
TTDOWNLOAD_DONTCARE

</td>
<td>
Unidrv can select the font format.

</td>
</tr>
<tr>
<td>
TTDOWNLOAD_GRAPHICS

</td>
<td>
Unidrv should print TrueType fonts as graphics, instead of downloading the font.

</td>
</tr>
<tr>
<td>
TTDOWNLOAD_TTOUTLINE

</td>
<td>
Unidrv should download the specified font as outlines. For more information, see the following Remarks section.

</td>
</tr>
</table>
 


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
The <code>IPrintOemUni::TTDownloadMethod</code> method's purpose is to allow a rendering plug-in to specify a printer's preferred format for a specified TrueType soft font.

If a rendering plug-in implements the <code>IPrintOemUni::TTDownloadMethod</code> method, Unidrv calls the method each time it is ready to send a TrueType font to the print spooler. Unidrv specifies the font type and the <code>IPrintOemUni::TTDownloadMethod</code> method should specify the printer's preferred format in the location pointed to by <i>pdwResult</i>.

The method should not return TTDOWNLOAD_TTOUTLINE unless the printer can rasterize TrueType fonts. The rendering plug-in is responsible for reading and parsing TrueType font files. Pointers to TrueType font files can be obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff566001">FONTOBJ_pvTrueTypeFontFile</a>.

The <code>IPrintOemUni::TTDownloadMethod</code> method is optional. If a rendering plug-in implements this method, the plug-in's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a> method must return S_OK when it receives "TTDownLoadMethod" as input.

For additional information see <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Customized Font Management</a>.


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
<a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a>
</dt>
<dt>
<a href="..\printoem\ns-printoem-_unifontobj.md">UNIFONTOBJ</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff566001">FONTOBJ_pvTrueTypeFontFile</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554253">IPrintOemUni::GetImplementedMethod</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUni::TTDownloadMethod method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

