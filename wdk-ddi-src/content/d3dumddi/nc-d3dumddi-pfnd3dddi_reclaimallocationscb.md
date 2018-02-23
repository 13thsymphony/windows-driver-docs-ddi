---
UID: NC:d3dumddi.PFND3DDDI_RECLAIMALLOCATIONSCB
title: PFND3DDDI_RECLAIMALLOCATIONSCB
author: windows-driver-content
description: Called by the user-mode display driver to reclaim video memory allocations that were previously offered for reuse.
old-location: display\pfnreclaimallocationscb.htm
old-project: display
ms.assetid: BAC27F24-B348-48D5-9E9B-20897B4D8E2D
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfnreclaimallocationscb, pfnReclaimAllocationsCb callback function [Display Devices], pfnReclaimAllocationsCb, PFND3DDDI_RECLAIMALLOCATIONSCB, PFND3DDDI_RECLAIMALLOCATIONSCB, d3dumddi/pfnReclaimAllocationsCb
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dumddi.h
apiname:
-	pfnReclaimAllocationsCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_RECLAIMALLOCATIONSCB callback function
Called by the user-mode display driver   to reclaim video memory allocations that were previously offered  for reuse.

## Syntax

```
PFND3DDDI_RECLAIMALLOCATIONSCB Pfnd3dddiReclaimallocationscb;

HRESULT Pfnd3dddiReclaimallocationscb(
  HANDLE hDevice,
  CONST D3DDDICB_RECLAIMALLOCATIONS *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

Returns one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The allocations were successfully reclaimed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was supplied.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
</td>
<td width="60%">
The video memory manager or display miniport driver could not complete the operation because either a Plug and Play (PnP) Stop event or a Timeout Detection and Recovery (TDR) event occurred.

<div class="alert"><b>Note</b>  If this error code is returned, the driver's calling function (typically the <a href="https://msdn.microsoft.com/AF3DCD16-9F8C-442A-A9A5-9EA2BD1C3B84">pfnReclaimResources</a> routine) must return this error code to the  Direct3D runtime.</div>
<div> </div>
</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicecallbacks.md">D3DDDI_DEVICECALLBACKS</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_reclaimallocations.md">D3DDDICB_RECLAIMALLOCATIONS</a>



<a href="https://msdn.microsoft.com/AF3DCD16-9F8C-442A-A9A5-9EA2BD1C3B84">pfnReclaimResources</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20pfnReclaimAllocationsCb callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>