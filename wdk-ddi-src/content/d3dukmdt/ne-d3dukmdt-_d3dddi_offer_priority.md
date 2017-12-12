---
UID: NE.d3dukmdt._D3DDDI_OFFER_PRIORITY
title: _D3DDDI_OFFER_PRIORITY
author: windows-driver-content
description: Indicates the importance of video memory resources that the user-mode display driver offers for reuse.
old-location: display\d3dddi_offer_priority.htm
old-project: display
ms.assetid: 2e43f782-c89c-4926-83db-efe737544065
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _D3DDDI_OFFER_PRIORITY, D3DDDI_OFFER_PRIORITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_OFFER_PRIORITY
req.alt-loc: D3dukmdt.h
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

# _D3DDDI_OFFER_PRIORITY enumeration



## -description
Indicates the importance of video memory resources  that the user-mode display driver offers for reuse.



## -syntax

````
typedef enum _D3DDDI_OFFER_PRIORITY { 
  D3DDDI_OFFER_PRIORITY_NONE    = 0,
  D3DDDI_OFFER_PRIORITY_LOW     = 1,
  D3DDDI_OFFER_PRIORITY_NORMAL  = 2,
  D3DDDI_OFFER_PRIORITY_HIGH    = 3,
  D3DDDI_OFFER_PRIORITY_AUTO    = 4
} D3DDDI_OFFER_PRIORITY;
````


## -enum-fields

### -field D3DDDI_OFFER_PRIORITY_NONE

The allocation should not be offered.

<div class="alert"><b>Note</b>  Do not use this value in the <a href="display.d3dddicb_offerallocations">D3DDDICB_OFFERALLOCATIONS</a>.<b>Priority</b> member.</div>
<div> </div>

### -field D3DDDI_OFFER_PRIORITY_LOW

The allocation has low value and should be discarded before other offered allocations. Specify this type for allocations that have no useful content.


### -field D3DDDI_OFFER_PRIORITY_NORMAL

The allocation has useful content but can easily be regenerated.


### -field D3DDDI_OFFER_PRIORITY_HIGH

The allocation has useful content and cannot easily be regenerated. The video memory manager (which is part of Dxgkrnl.sys) should therefore avoid discarding this allocation before other offered allocations.


### -field D3DDDI_OFFER_PRIORITY_AUTO

The video memory manager should make a policy decision on the allocation's value based on its  priority for eviction.


## -remarks


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
<dt>D3dukmdt.h (include D3dumddi.h or D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dddi_allocationlist">D3DDDI_ALLOCATIONLIST</a>
</dt>
<dt>
<a href="display.d3dddicb_offerallocations">D3DDDICB_OFFERALLOCATIONS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_OFFER_PRIORITY enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

