---
UID: NC.d3dumddi.PFND3DDDI_OFFERRESOURCES
title: PFND3DDDI_OFFERRESOURCES
author: windows-driver-content
description: Called by the Microsoft Direct3D runtime to request that the user-mode display driver offer video memory resources for reuse.
old-location: display\offerresources.htm
old-project: display
ms.assetid: 68551AD7-AC0C-4138-948F-33773F02DA41
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OfferResources
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

# PFND3DDDI_OFFERRESOURCES callback



## -description
Called by the Microsoft Direct3D runtime to request that the user-mode display driver  offer video memory resources for reuse.


## -prototype

````
PFND3DDDI_OFFERRESOURCES OfferResources;

_Check_return_ HRESULT APIENTRY* OfferResources(
  _In_       HANDLE                   hDevice,
  _In_ const D3DDDIARG_OFFERRESOURCES *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).

### -param pData [in]

 A pointer to a <a href="display.d3dddiarg_offerresources">D3DDDIARG_OFFERRESOURCES</a> structure that defines the video memory resources that the driver offers.

## -returns

       Returns one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The video memory resources were successfully offered.
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
         The driver detected that the display adapter was removed, so the driver did not complete the operation.

If the driver is not aware of the adapter removal, the driver is not required to return this error code.

 

## -remarks
If the user-mode driver does not have outstanding work queued that references an allocation that it has been asked to offer, then it can offer the allocation immediately or postpone the offer until the next call is made to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flush.md">Flush</a> or <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_present.md">Present</a> functions. However, the driver must always process all batched offer calls that have been submitted through <i>Flush</i> or <i>Present</i>.

If the driver uses the <a href="https://msdn.microsoft.com/f22e19ba-9ff3-4aa1-a3f0-103f67ea7c60">renaming service</a> of the video memory manager, then the driver should offer the last allocation instance.

## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 8
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2012
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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dddiarg_offerresources">D3DDDIARG_OFFERRESOURCES</a>
</dt>
<dt>
<a href="display.d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_flush.md">Flush</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_present.md">Present</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reclaimresources.md">ReclaimResources</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_OFFERRESOURCES callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
