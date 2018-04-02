---
UID: NC:d3dkmddi.DXGKDDI_VIDPN_GETTOPOLOGY
title: DXGKDDI_VIDPN_GETTOPOLOGY
author: windows-driver-content
description: The pfnGetTopology function returns a handle to the VidPN topology object contained by a specified VidPN object.
old-location: display\dxgk_vidpn_interface_pfngettopology.htm
old-project: display
ms.assetid: 2bc43cd0-97a2-4120-8e6f-425664d3d28c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_VIDPN_GETTOPOLOGY, VidPnFunctions_2818281e-102f-4c76-a57d-3b133b0692e6.xml, d3dkmddi/pfnGetTopology, display.dxgk_vidpn_interface_pfngettopology, pfnGetTopology, pfnGetTopology callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	pfnGetTopology
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_VIDPN_GETTOPOLOGY callback function
The <b>pfnGetTopology</b> function returns a handle to the VidPN topology object contained by a specified VidPN object.

## Syntax

```
DXGKDDI_VIDPN_GETTOPOLOGY DxgkddiVidpnGettopology;

NTSTATUS DxgkddiVidpnGettopology(
  IN_CONST_D3DKMDT_HVIDPN hVidPn,
  OUT_PD3DKMDT_HVIDPNTOPOLOGY phVidPnTopology,
  DEREF_OUT_CONST_PPDXGK_VIDPNTOPOLOGY_INTERFACE ppVidPnTopologyInterface
)
{...}
```

## Parameters

`hVidPn`

[in] A handle to a VidPN object. The VidPN manager previously provided this handle to the display miniport driver by calling <a href="https://msdn.microsoft.com/6dda82bd-1a43-4ffe-b398-a9f8cee6d1c1">DxgkDdiEnumVidPnCofuncModality</a>, <a href="https://msdn.microsoft.com/96e96366-6306-4d20-8752-e942f2ed4069">DxgkDdiIsSupportedVidPn</a>, or <a href="https://msdn.microsoft.com/320a77a7-d7d4-47b9-8a40-2b6e12819e4b">DxgkDdiRecommendFunctionalVidPn</a>.

`phVidPnTopology`

[out] A pointer to a variable that receives a handle to the VidPN topology object.

`ppVidPnTopologyInterface`

[out] A pointer to a variable that receives a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff562091">DXGK_VIDPNTOPOLOGY_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can call to inspect and alter the VidPN topology object.


## Return Value

The <b>pfnGetTopology</b> function returns one of the following values:

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
The function succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPn</i> was invalid.

</td>
</tr>
</table>

## Remarks

The display miniport driver does not need to release the handle that it receives in <i>phVidPnTopology</i>.

The lifetime of the DXGK_VIDPNTOPOLOGY_INTERFACE structure returned in <i>ppVidPnTopologyInterface</i> is owned by the operating system. Using this ownership scheme, the operating system can migrate to newer implementations at run time without breaking clients of the interface.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff562091">DXGK_VIDPNTOPOLOGY_INTERFACE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570560">VidPN Topology Interface</a>