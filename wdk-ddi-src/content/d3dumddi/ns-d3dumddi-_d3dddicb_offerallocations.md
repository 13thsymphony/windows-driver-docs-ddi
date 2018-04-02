---
UID: NS:d3dumddi._D3DDDICB_OFFERALLOCATIONS
title: "_D3DDDICB_OFFERALLOCATIONS"
author: windows-driver-content
description: Defines the video memory allocations that the driver offers for reuse. Used with the pfnOfferAllocationsCb function.
old-location: display\d3dddicb_offerallocations.htm
old-project: display
ms.assetid: 26f3cd7b-ae2e-4632-bfb2-e62839346f83
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDICB_OFFERALLOCATIONS, D3DDDICB_OFFERALLOCATIONS structure [Display Devices], _D3DDDICB_OFFERALLOCATIONS, d3dumddi/D3DDDICB_OFFERALLOCATIONS, display.d3dddicb_offerallocations
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
-	D3dumddi.h
api_name:
-	D3DDDICB_OFFERALLOCATIONS
product: Windows
targetos: Windows
req.typenames: D3DDDICB_OFFERALLOCATIONS
---

# _D3DDDICB_OFFERALLOCATIONS structure
Defines the video memory allocations that the driver offers for reuse. Used with the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451693">pfnOfferAllocationsCb</a> function.

## Syntax
```
typedef struct _D3DDDICB_OFFERALLOCATIONS {
  CONST HANDLE          *pResources;
  CONST D3DKMT_HANDLE   *HandleList;
  UINT                  NumAllocations;
  D3DDDI_OFFER_PRIORITY Priority;
} D3DDDICB_OFFERALLOCATIONS;
```

## Members


`pResources`

[in] An array of Direct3D runtime handles to resources to offer.

If the user-mode driver uses the array specified by <b>HandleList</b> to offer a list of allocations, it must set <b>pResources</b> to <b>NULL</b>. Conversely, if the driver uses the array specified by <b>pResources</b> to offer a list of resources, it must set <b>HandleList</b> to <b>NULL</b>.

`HandleList`

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to allocations to offer.

If resources were created with the <b>D3D10_DDI_BIND_PRESENT</b> flag value set in <i>pCreateResource</i>-&gt;<b>BindFlags</b>, offer the resources by their allocation handles, not by their resource handles.

`NumAllocations`

[in] The number of items in the <b>pResources</b> or <b>HandleList</b> members, whichever is not <b>NULL</b>.

`Priority`

[in] The priority, of type  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439275">D3DDDI_OFFER_PRIORITY</a>, with which to offer the allocations for reuse.

<div class="alert"><b>Note</b>  Do not set this member to a value of <b>D3DDDI_OFFER_PRIORITY_NONE</b>.</div>
<div> </div>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/2dff9d2e-c497-422f-824b-a7101904fd67">CreateResource(D3D11)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439275">D3DDDI_OFFER_PRIORITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451693">pfnOfferAllocationsCb</a>