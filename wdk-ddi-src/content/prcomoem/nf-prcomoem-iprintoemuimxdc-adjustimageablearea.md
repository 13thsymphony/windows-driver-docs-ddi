---
UID: NF.prcomoem.IPrintOemUIMXDC.AdjustImageableArea
title: IPrintOemUIMXDC::AdjustImageableArea
author: windows-driver-content
description: The IPrintOemUIMXDC::AdjustImageableArea method enables an XPS filter pipeline driver to use UnidrvUI.dll or PS5UI.dll to support configuration of the printable area, including orientation and direction of rotation.
old-location: print\iprintoemuimxdc_adjustimageablearea.htm
old-project: print
ms.assetid: a698fcb9-1285-4201-9b49-e79dcda66043
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IPrintOemUIMXDC, AdjustImageableArea, IPrintOemUIMXDC::AdjustImageableArea
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: Available with Windows Vista and later versions of Unidrvui.dll and Ps5ui.dll, which are redistributable. This method is also available for XPSDrv drivers in Microsoft Windows XP if you have installed the XPS Essentials Pack.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintOemUIMXDC.AdjustImageableArea
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
req.iface: IPrintOemUIMXDC
req.product: Windows 10 or later.
---

# IPrintOemUIMXDC::AdjustImageableArea method



## -description
<p>The <code>IPrintOemUIMXDC::AdjustImageableArea</code> method enables an XPS filter pipeline driver to use UnidrvUI.dll or PS5UI.dll to support configuration of the printable area, including orientation and direction of rotation.</p>


## -syntax

````
HRESULT AdjustImageableArea(
         HANDLE   hPrinter,
         DWORD    cbDevMode,
   const PDEVMODE pDevMode,
         DWORD    cbOEMDM,
   const PVOID    pOEMDM,
         PRECTL   prclImageableArea
);
````


## -parameters
<dl>

### -param <i>hPrinter</i> 

<dd>
<p>A handle to the printer that is currently being queried.</p>
</dd>

### -param <i>cbDevMode</i> 

<dd>
<p>The size of the <a href="display.devmodew">DEVMODE</a> structure, in bytes, including appended data.</p>
</dd>

### -param <i>pDevMode</i> 

<dd>
<p>A pointer to the DEVMODE structure that contains the current device settings.</p>
</dd>

### -param <i>cbOEMDM</i> 

<dd>
<p>The number of bytes in the vendor-provided section of the DEVMODE structure.</p>
</dd>

### -param <i>pOEMDM</i> 

<dd>
<p>A pointer to the data that is contained in the vendor portion of the DEVMODE structure that <i>pDevMode</i> points to.</p>
</dd>

### -param <i>prclImageableArea</i> 

<dd>
<p>A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569236">RECTL</a> structure that contains the printable area. This parameter is populated by UnidrvUI.dll or PS5UI.dll with data from the corresponding GPD or PPD, before the parameter is passed to the plug-in. The plug-in can then update this data before returning. </p>
</dd>
</dl>

## -returns
<p><code>AdjustImageableArea</code> returns S_OK if this method succeeds. Otherwise, this method should return E_NOTIMPL if the plug-in does not support the method, or any appropriate failure value if the plug-in cannot complete the operation. For more information, see the following Remarks section.</p>

## -remarks
<p>The <i>prclImageableArea</i> parameter is IN OUT. All other parameters for this method are input only.</p>

<p>If the plug-in cannot complete the operation, it should return an appropriate failure HRESULT value, which willcause the current print job to fail.</p>

<p>The <i>prclImageableArea</i> parameter is IN OUT. All other parameters for this method are input only.</p>

<p>If the plug-in cannot complete the operation, it should return an appropriate failure HRESULT value, which willcause the current print job to fail.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available with Windows Vista and later versions of Unidrvui.dll and Ps5ui.dll, which are redistributable. This method is also available for XPSDrv drivers in Microsoft Windows XP if you have installed the XPS Essentials Pack.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569236">RECTL</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemUIMXDC::AdjustImageableArea method%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
