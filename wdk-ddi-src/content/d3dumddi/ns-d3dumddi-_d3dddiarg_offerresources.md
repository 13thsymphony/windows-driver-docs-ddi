---
UID: NS.D3DUMDDI._D3DDDIARG_OFFERRESOURCES
title: _D3DDDIARG_OFFERRESOURCES
author: windows-driver-content
description: Describes video memory resources that the user-mode display driver offers for reuse. Used with the OfferResources function.
old-location: display\d3dddiarg_offerresources.htm
old-project: display
ms.assetid: 3c5e5dae-14f6-47b9-8c27-48ecc73a43ef
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DDDIARG_OFFERRESOURCES, D3DDDIARG_OFFERRESOURCES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_OFFERRESOURCES
req.alt-loc: D3dumddi.h
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

# _D3DDDIARG_OFFERRESOURCES structure



## -description
 Describes video memory resources that the user-mode display driver offers for reuse. Used with the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_offerresources.md">OfferResources</a>  function.


## -syntax

````
typedef struct _D3DDDIARG_OFFERRESOURCES {
  const HANDLE          *pResources;
  UINT                  Resources;
  D3DDDI_OFFER_PRIORITY Priority;
} D3DDDIARG_OFFERRESOURCES;
````


## -struct-fields

### -field pResources

[in] A pointer to an array of handles to the video memory resources that the driver offers.

### -field Resources

[in] The number of elements in the array pointed to by <b>pResources</b>.

### -field Priority

[in] A value of type <a href="display.d3dddi_offer_priority">D3DDDI_OFFER_PRIORITY</a> that indicates the importance of the resources pointed to by <b>pResources</b>.

## -remarks
This structure is pointed to by  the <i>pData</i> parameter of the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_offerresources.md">OfferResources</a> routine.

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
<a href="display.d3dddi_offer_priority">D3DDDI_OFFER_PRIORITY</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_offerresources.md">OfferResources</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_OFFERRESOURCES structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
