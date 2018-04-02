---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO
title: DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO
author: windows-driver-content
description: The pfnAcquireNextPathInfo function returns a descriptor of the next video present path in a specified VidPN topology, given the current path.
old-location: display\dxgk_vidpntopology_interface_pfnacquirenextpathinfo.htm
old-project: display
ms.assetid: 9f09ac0e-057c-48fb-a246-35e8ed7ddfc2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO, VidPnFunctions_c06f9c56-bcfd-49a8-a723-4166d7f5129f.xml, d3dkmddi/pfnAcquireNextPathInfo, display.dxgk_vidpntopology_interface_pfnacquirenextpathinfo, pfnAcquireNextPathInfo, pfnAcquireNextPathInfo callback function [Display Devices]
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
-	pfnAcquireNextPathInfo
product:
- Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO callback function
The <b>pfnAcquireNextPathInfo</b> function returns a descriptor of the next video present path in a specified VidPN topology, given the current path.

## Syntax

```
DXGKDDI_VIDPNTOPOLOGY_ACQUIRENEXTPATHINFO DxgkddiVidpntopologyAcquirenextpathinfo;

NTSTATUS DxgkddiVidpntopologyAcquirenextpathinfo(
  IN_CONST_D3DKMDT_HVIDPNTOPOLOGY hVidPnTopology,
  IN_CONST_PD3DKMDT_VIDPN_PRESENT_PATH_CONST pVidPnPresentPathInfo,
  DEREF_OUT_CONST_PPD3DKMDT_VIDPN_PRESENT_PATH ppNextVidPnPresentPathInfo
)
{...}
```

## Parameters

`hVidPnTopology`

[in] A handle to a VidPN topology object. The display miniport driver previously obtained this handle by calling the <a href="https://msdn.microsoft.com/2bc43cd0-97a2-4120-8e6f-425664d3d28c">pfnGetTopology</a> function of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562108">DXGK_VIDPN_INTERFACE</a> interface.

`pVidPnPresentPathInfo`

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a> structure that describes the current path. The display miniport driver previously obtained this pointer by calling <a href="https://msdn.microsoft.com/b5dc35dc-f4fb-4209-9a4d-50dc11f16216">pfnAcquireFirstPathInfo</a> or <b>pfnAcquireNextPathInfo</b>.

`ppNextVidPnPresentPathInfo`

[out] A pointer to a variable that receives a pointer to a D3DKMDT_VIDPN_PRESENT_PATH structure that describes the next path.


## Return Value

The <b>pfnAcquireNextPathInfo</b> function returns one of the following values:

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
<dt><b>STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hVidPnTopology </i>was invalid.

</td>
</tr>
</table>

## Remarks

When you have finished using the D3DKMDT_VIDPN_PRESENT_PATH structure, you must release the structure by calling <a href="https://msdn.microsoft.com/fdd34377-6b11-4005-93f1-ab42be7633c2">pfnReleasePathInfo</a>.

You can enumerate all the paths that belong to a VidPN topology object by calling <a href="https://msdn.microsoft.com/b5dc35dc-f4fb-4209-9a4d-50dc11f16216">pfnAcquireFirstPathInfo</a> and then making a sequence of calls to <b>pfnAcquireNextPathInfo</b>.

The D3DKMDT_HVIDPNTOPOLOGY data type is defined in <i>D3dkmdt.h</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="https://msdn.microsoft.com/27a03106-a5b5-489c-968a-81b3ea9940cb">pfnAcqirePathInfo</a>



<a href="https://msdn.microsoft.com/b5dc35dc-f4fb-4209-9a4d-50dc11f16216">pfnAcquireFirstPathInfo</a>



<a href="https://msdn.microsoft.com/fdd34377-6b11-4005-93f1-ab42be7633c2">pfnReleasePathInfo</a>