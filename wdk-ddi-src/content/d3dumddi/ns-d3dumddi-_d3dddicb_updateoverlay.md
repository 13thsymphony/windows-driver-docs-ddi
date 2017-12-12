---
UID: NS.D3DUMDDI._D3DDDICB_UPDATEOVERLAY
title: _D3DDDICB_UPDATEOVERLAY
author: windows-driver-content
description: The D3DDDICB_UPDATEOVERLAY structure describes parameters for modifying an overlay.
old-location: display\d3dddicb_updateoverlay.htm
old-project: display
ms.assetid: efa54d23-99bc-49ea-b8a3-7ea5b00e36d8
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DDDICB_UPDATEOVERLAY, D3DDDICB_UPDATEOVERLAY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDICB_UPDATEOVERLAY
req.alt-loc: d3dumddi.h
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

# _D3DDDICB_UPDATEOVERLAY structure



## -description
The D3DDDICB_UPDATEOVERLAY structure describes parameters for modifying an overlay.



## -syntax

````
typedef struct _D3DDDICB_UPDATEOVERLAY {
  D3DKMT_HANDLE            hKernelOverlay;
  D3DDDI_KERNELOVERLAYINFO OverlayInfo;
} D3DDDICB_UPDATEOVERLAY;
````


## -struct-fields

### -field hKernelOverlay

[in] A D3DKMT_HANDLE data type that represents the kernel-mode handle that is returned by the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlaycb.md">pfnCreateOverlayCb</a> function and that identifies the kernel-mode overlay object to modify. 


### -field OverlayInfo

[in] A <a href="display.d3dddi_kerneloverlayinfo">D3DDDI_KERNELOVERLAYINFO</a> structure that describes modification information for the kernel-mode overlay object. 


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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dddi_kerneloverlayinfo">D3DDDI_KERNELOVERLAYINFO</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlaycb.md">pfnCreateOverlayCb</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateoverlaycb.md">pfnUpdateOverlayCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_UPDATEOVERLAY structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

