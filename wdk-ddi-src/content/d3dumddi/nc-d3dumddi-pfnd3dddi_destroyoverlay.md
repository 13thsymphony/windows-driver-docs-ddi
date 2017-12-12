---
UID: NC.d3dumddi.PFND3DDDI_DESTROYOVERLAY
title: PFND3DDDI_DESTROYOVERLAY
author: windows-driver-content
description: The DestroyOverlay function disables the overlay hardware and frees the overlay handle.
old-location: display\destroyoverlay.htm
old-project: display
ms.assetid: 63004d19-e2cd-462c-8fa5-ea4dd6e29735
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DestroyOverlay
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

# PFND3DDDI_DESTROYOVERLAY callback



## -description
The <b>DestroyOverlay</b> function disables the overlay hardware and frees the overlay handle.



## -prototype

````
PFND3DDDI_DESTROYOVERLAY DestroyOverlay;

__checkReturn HRESULT APIENTRY DestroyOverlay(
  _In_       HANDLE                   hDevice,
  _In_ const D3DDDIARG_DESTROYOVERLAY *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in]

 A pointer to a <a href="display.d3dddiarg_destroyoverlay">D3DDDIARG_DESTROYOVERLAY</a> structure that contains the overlay handle.


## -returns
<b>DestroyOverlay</b> returns S_OK or an appropriate error result if the overlay hardware is not disabled.


## -remarks
Overlays are independent from the resources that are displayed by using the overlays.


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
<a href="display.d3dddiarg_destroyoverlay">D3DDDIARG_DESTROYOVERLAY</a>
</dt>
<dt>
<a href="display.d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_DESTROYOVERLAY callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

