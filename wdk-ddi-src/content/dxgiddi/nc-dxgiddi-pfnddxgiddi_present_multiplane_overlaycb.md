---
UID: NC.dxgiddi.PFNDDXGIDDI_PRESENT_MULTIPLANE_OVERLAYCB
title: PFNDDXGIDDI_PRESENT_MULTIPLANE_OVERLAYCB
author: windows-driver-content
description: Called by the Microsoft DirectX Graphics Infrastructure (DXGI) runtime to notify the user-mode display driver that an application finished rendering and requests that the driver display the source surface by either copying or flipping or that the driver perform a color-fill operation. Must be implemented by Windows Display Driver Model (WDDM) 1.3 or later drivers that support multiplane overlays.
old-location: display\pfnpresentmultiplaneoverlay__dxgi_.htm
old-project: display
ms.assetid: C6EB96AC-0D5B-4D75-9B44-B1744F6A4360
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: DxApiGetVersion
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnPresentMultiPlaneOverlayCb
req.alt-loc: Dxgiddi.h
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
---

# PFNDDXGIDDI_PRESENT_MULTIPLANE_OVERLAYCB callback



## -description
Called by the Microsoft DirectX Graphics Infrastructure (DXGI) runtime to notify  the user-mode display driver that an application finished rendering and requests that the driver display the source surface by either copying or flipping or that the driver perform a color-fill operation. Must be implemented by Windows Display Driver Model (WDDM) 1.3 or later drivers that support multiplane overlays.



## -prototype

````
PFNDDXGIDDI_PRESENT_MULTIPLANE_OVERLAYCB pfnPresentMultiPlaneOverlayCb;

HRESULT __stdcall* pfnPresentMultiPlaneOverlayCb(
   DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY *pPresentDXGI
)
{ ... }
````


## -parameters

### -param pPresentDXGI 

A pointer to a <a href="display.dxgi_ddi_arg_presentmultiplaneoverlay">DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY</a> structure that describes how to display to the destination surface. 


## -returns
If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks
When the user-mode display driver successfully completes its processing of a call to this function, it presents the source surface to the display by calling the <a href="display.pfnpresentmultiplaneoverlaycb_dxgi">pfnPresentMultiPlaneOverlayCb (DXGI)</a> function.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
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
<dt>Dxgiddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgi_ddi_arg_presentmultiplaneoverlay">DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY</a>
</dt>
<dt>
<a href="display.pfnpresentmultiplaneoverlaycb_dxgi">pfnPresentMultiPlaneOverlayCb (DXGI)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFNDDXGIDDI_PRESENT_MULTIPLANE_OVERLAYCB callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

