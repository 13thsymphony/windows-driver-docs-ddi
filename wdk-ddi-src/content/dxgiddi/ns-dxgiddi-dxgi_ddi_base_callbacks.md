---
UID: NS.DXGIDDI.DXGI_DDI_BASE_CALLBACKS
title: DXGI_DDI_BASE_CALLBACKS
author: windows-driver-content
description: The DXGI_DDI_BASE_CALLBACKS structure contains pointers to Microsoft Direct3D 10 runtime callback functions that the user-mode display driver can use.
old-location: display\dxgi_ddi_base_callbacks.htm
old-project: display
ms.assetid: dd1690e2-7eef-4086-a3e1-9ca456b79a6f
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: DXGI_DDI_BASE_CALLBACKS, DXGI_DDI_BASE_CALLBACKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGI_DDI_BASE_CALLBACKS
req.alt-loc: dxgiddi.h
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

# DXGI_DDI_BASE_CALLBACKS structure



## -description
The DXGI_DDI_BASE_CALLBACKS structure contains pointers to Microsoft Direct3D 10 runtime callback functions that the user-mode display driver can use.



## -syntax

````
typedef struct DXGI_DDI_BASE_CALLBACKS {
  PFNDDXGIDDI_PRESENTCB                    pfnPresentCb;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN8)
  PFNDDXGIDDI_PRESENT_MULTIPLANE_OVERLAYCB pfnPresentMultiplaneOverlayCb;
#endif 
} DXGI_DDI_BASE_CALLBACKS;
````


## -struct-fields

### -field pfnPresentCb

A pointer to the <a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_presentcb.md">pfnPresentCbDXGI</a> function.


### -field pfnPresentMultiplaneOverlayCb

A pointer to the <a href="display.pfnpresentmultiplaneoverlaycb_dxgi">pfnPresentMultiPlaneOverlayCb (DXGI)</a> function. Supported starting with Windows 8.1.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a>
</dt>
<dt>
<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_base_args.md">DXGI_DDI_BASE_ARGS</a>
</dt>
<dt>
<a href="..\dxgiddi\nc-dxgiddi-pfnddxgiddi_presentcb.md">pfnPresentCbDXGI</a>
</dt>
<dt>
<a href="display.pfnpresentmultiplaneoverlaycb_dxgi">pfnPresentMultiPlaneOverlayCb (DXGI)</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGI_DDI_BASE_CALLBACKS structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

