---
UID: NF:d3dkmthk.D3DKMTOfferAllocations
title: D3DKMTOfferAllocations function
author: windows-driver-content
description: Offers video memory allocations for reuse.
old-location: display\d3dkmtofferallocations.htm
old-project: display
ms.assetid: 3cc84381-fa1e-4c6c-bb5b-459a93676cfd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMTOfferAllocations, D3DKMTOfferAllocations callback function [Display Devices], PFND3DKMT_OFFERALLOCATIONS, d3dkmthk/D3DKMTOfferAllocations, display.d3dkmtofferallocations
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
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
-	UserDefined
api_location:
-	D3dkmthk.h
api_name:
-	D3DKMTOfferAllocations
product: Windows
targetos: Windows
req.typenames: D3DKMT_DRIVERVERSION
---


# D3DKMTOfferAllocations function
Offers video memory allocations for reuse.

## Syntax

````
EXTERN_C _Check_return_ NTSTATUS APIENTRY D3DKMTOfferAllocations(
  _In_ const D3DKMT_OFFERALLOCATIONS *pData
);
````

## Parameters

`D3DKMT_OFFERALLOCATIONS`

TBD


## Return Value

Returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The allocations were successfully offered.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was stopped or the display device was reset.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Universal |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_offerallocations.md">D3DKMT_OFFERALLOCATIONS</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtreclaimallocations.md">D3DKMTReclaimAllocations</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DKMT_OFFERALLOCATIONS callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>