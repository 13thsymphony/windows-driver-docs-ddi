---
UID: NS.dxgiddi._DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY
title: DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY
author: windows-driver-content
description: Specifies a multiplane overlay resource to display.
old-location: display\dxgi_ddi_arg_presentmultiplaneoverlay.htm
old-project: display
ms.assetid: 3d965c9b-1d71-4ef5-9b76-391b36b1d8c7
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY, DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY
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
req.iface: 
---

# DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY structure



## -description
<p>Specifies a multiplane overlay resource to display.</p>


## -syntax

````
typedef struct _DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY {
  DXGI_DDI_HDEVICE                    hDevice;
  void                                *pDXGIContext;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID      VidPnSourceId;
  DXGI_DDI_PRESENT_FLAGS              Flags;
  DXGI_DDI_FLIP_INTERVAL_TYPE         FlipInterval;
  UINT                                PresentPlaneCount;
  DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY *pPresentPlanes;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WDDM1_3)
  UINT                                Reserved;
#endif 
} DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY;
````


## -struct-fields
<dl>

### -field <b>hDevice</b>

<dd>
<p>[in] A handle to the display device (graphics context) on which the driver performs the presentation. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg-createdevice.md">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createdevice.md">CreateDevice(D3D10)</a> function to create the display device. </p>
</dd>

### -field <b>pDXGIContext</b>

<dd>
<p>[in] A handle to the DXGI context. This handle is opaque to the driver. The driver should assign the handle in this member to the <b>pDXGIContext</b> member of the <a href="..\dxgiddi\ns-dxgiddi-dxgiddicb-present-multiplane-overlay.md">DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY</a> structure when the driver calls the <a href="display.pfnpresentmultiplaneoverlaycb_dxgi">pfnPresentMultiPlaneOverlayCb (DXGI)</a> function. </p>
</dd>

### -field <b>VidPnSourceId</b>

<dd>
<p>[in] The zero-based video present network (VidPN) source identification number of the input that is to be displayed.</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>[in] A <a href="..\dxgiddi\ns-dxgiddi-dxgi-ddi-present-flags.md">DXGI_DDI_PRESENT_FLAGS</a> structure that identifies, in bit-field flags, how to display.</p>
</dd>

### -field <b>FlipInterval</b>

<dd>
<p>[in] A value of type <a href="..\dxgiddi\ne-dxgiddi-dxgi-ddi-flip-interval-type.md">DXGI_DDI_FLIP_INTERVAL_TYPE</a> that indicates the flip interval (that is, if the flip occurs after zero, one, two, three, or four vertical syncs). </p>
</dd>

### -field <b>PresentPlaneCount</b>

<dd>
<p>[in] The number of overlay planes that are available to display.</p>
</dd>

### -field <b>pPresentPlanes</b>

<dd>
<p>[in] A pointer to a structure of type <a href="..\dxgiddi\ns-dxgiddi--dxgi-ddi-present-multiplane-overlay.md">DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY</a> that  describes the overlay plane to display.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>This member is reserved and should be set to zero.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createdevice.md">CreateDevice(D3D10)</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg-createdevice.md">D3D10DDIARG_CREATEDEVICE</a>
</dt>
<dt>
<a href="..\dxgiddi\ne-dxgiddi-dxgi-ddi-flip-interval-type.md">DXGI_DDI_FLIP_INTERVAL_TYPE</a>
</dt>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi-ddi-present-flags.md">DXGI_DDI_PRESENT_FLAGS</a>
</dt>
<dt>
<a href="..\dxgiddi\ns-dxgiddi--dxgi-ddi-present-multiplane-overlay.md">DXGI_DDI_PRESENT_MULTIPLANE_OVERLAY</a>
</dt>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgiddicb-present-multiplane-overlay.md">DXGIDDICB_PRESENT_MULTIPLANE_OVERLAY</a>
</dt>
<dt>
<a href="display.pfnpresentmultiplaneoverlaycb_dxgi">pfnPresentMultiPlaneOverlayCb (DXGI)</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_ARG_PRESENTMULTIPLANEOVERLAY structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
