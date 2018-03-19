---
UID: NE:d3dukmdt._D3DDDI_OFFER_PRIORITY
title: "_D3DDDI_OFFER_PRIORITY"
author: windows-driver-content
description: Indicates the importance of video memory resources that the user-mode display driver offers for reuse.
old-location: display\d3dddi_offer_priority.htm
old-project: display
ms.assetid: 2e43f782-c89c-4926-83db-efe737544065
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDI_OFFER_PRIORITY, D3DDDI_OFFER_PRIORITY enumeration [Display Devices], D3DDDI_OFFER_PRIORITY_AUTO, D3DDDI_OFFER_PRIORITY_HIGH, D3DDDI_OFFER_PRIORITY_LOW, D3DDDI_OFFER_PRIORITY_NONE, D3DDDI_OFFER_PRIORITY_NORMAL, _D3DDDI_OFFER_PRIORITY, d3dukmdt/D3DDDI_OFFER_PRIORITY, d3dukmdt/D3DDDI_OFFER_PRIORITY_AUTO, d3dukmdt/D3DDDI_OFFER_PRIORITY_HIGH, d3dukmdt/D3DDDI_OFFER_PRIORITY_LOW, d3dukmdt/D3DDDI_OFFER_PRIORITY_NONE, d3dukmdt/D3DDDI_OFFER_PRIORITY_NORMAL, display.d3dddi_offer_priority
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dukmdt.h
api_name:
-	D3DDDI_OFFER_PRIORITY
product: Windows
targetos: Windows
req.typenames: D3DDDI_OFFER_PRIORITY
---

# _D3DDDI_OFFER_PRIORITY Enumeration
Indicates the importance of video memory resources  that the user-mode display driver offers for reuse.

## Syntax
````
typedef enum _D3DDDI_OFFER_PRIORITY { 
  D3DDDI_OFFER_PRIORITY_NONE    = 0,
  D3DDDI_OFFER_PRIORITY_LOW     = 1,
  D3DDDI_OFFER_PRIORITY_NORMAL  = 2,
  D3DDDI_OFFER_PRIORITY_HIGH    = 3,
  D3DDDI_OFFER_PRIORITY_AUTO    = 4
} D3DDDI_OFFER_PRIORITY;
````

## Constants

<table>
            
                <tr>
                    <td>D3DDDI_OFFER_PRIORITY_NONE</td>
                    <td>The allocation should not be offered.

<div class="alert"><b>Note</b>  Do not use this value in the <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_offerallocations.md">D3DDDICB_OFFERALLOCATIONS</a>.<b>Priority</b> member.</div>
<div> </div></td>
                </tr>
            
                <tr>
                    <td>D3DDDI_OFFER_PRIORITY_LOW</td>
                    <td>The allocation has low value and should be discarded before other offered allocations. Specify this type for allocations that have no useful content.</td>
                </tr>
            
                <tr>
                    <td>D3DDDI_OFFER_PRIORITY_NORMAL</td>
                    <td>The allocation has useful content but can easily be regenerated.</td>
                </tr>
            
                <tr>
                    <td>D3DDDI_OFFER_PRIORITY_HIGH</td>
                    <td>The allocation has useful content and cannot easily be regenerated. The video memory manager (which is part of Dxgkrnl.sys) should therefore avoid discarding this allocation before other offered allocations.</td>
                </tr>
            
                <tr>
                    <td>D3DDDI_OFFER_PRIORITY_AUTO</td>
                    <td>The video memory manager should make a policy decision on the allocation's value based on its  priority for eviction.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dukmdt.h (include D3dumddi.h, D3dkmddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_offerallocations.md">D3DDDICB_OFFERALLOCATIONS</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationlist.md">D3DDDI_ALLOCATIONLIST</a>