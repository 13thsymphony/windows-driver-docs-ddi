---
UID: NC:d3dkmddi.DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET
title: DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET
author: windows-driver-content
description: The pfnReleaseAdditionalMonitorModeSet function, available in the DXGK_MONITOR_INTERFACE_V2 interface beginning with Windows 7, releases a handle to an additional monitor source mode set object that is associated with a specified monitor.
old-location: display\dxgk_monitor_interface_v2_pfnreleaseadditionalmonitormodeset.htm
old-project: display
ms.assetid: b9f6cb52-8870-4319-a1ff-d3dbbeef8cb6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET, VidPnFunctions_7b298754-19ed-420f-88f9-2910c3f5968a.xml, d3dkmddi/pfnReleaseAdditionalMonitorModeSet, display.dxgk_monitor_interface_v2_pfnreleaseadditionalmonitormodeset, pfnReleaseAdditionalMonitorModeSet, pfnReleaseAdditionalMonitorModeSet callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
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
-	pfnReleaseAdditionalMonitorModeSet
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET callback function
The <b>pfnReleaseAdditionalMonitorModeSet</b> function, available in the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_monitor_interface_v2.md">DXGK_MONITOR_INTERFACE_V2</a> interface beginning with Windows 7, releases a handle to an additional monitor source mode set object that is associated with a specified monitor.

## Syntax

```
DXGKDDI_MONITOR_RELEASEADDITIONALMONITORMODESET DxgkddiMonitorReleaseadditionalmonitormodeset;

NTSTATUS DxgkddiMonitorReleaseadditionalmonitormodeset(
  IN_CONST_D3DKMDT_ADAPTER hAdapter,
  IN_CONST_D3DDDI_VIDEO_PRESENT_TARGET_ID VideoPresentTargetId,
  IN_CONST_PDXGK_TARGETMODE_DETAIL_TIMING pAdditionalModesSet
)
{...}
```

## Parameters

`hAdapter`

[in] A handle that identifies a display adapter. The Microsoft DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.

`VideoPresentTargetId`

[in] An integer that identifies one of the video present targets on the display adapter. The additional modes set object <i>ppAdditionalModesSet</i> returned in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_getadditionalmonitormodeset.md">pfnGetAdditionalMonitorModeSet</a> function describes the additional monitor source mode sets that are available on the monitor that is connected to this video present target.

`pAdditionalModesSet`

[in] A pointer to a variable that receives a <a href="..\d3dkmdt\ns-d3dkmdt-_dxgk_targetmode_detail_timing.md">DXGK_TARGETMODE_DETAIL_TIMING</a> structure that describes a video present target's additional timing modes that are compatible with the display device. This structure was initially obtained in a call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_getadditionalmonitormodeset.md">pfnGetAdditionalMonitorModeSet</a>.


## Return Value

The <b>pfnReleaseAdditionalMonitorModeSet</b> function returns one of the following values.

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
<dt><b>STATUS_GRAPHICS_INVALID_DISPLAY_ADAPTER</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>hAdapter</i> was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_MONITOR_SOURCEMODESET</b></dt>
</dl>
</td>
<td width="60%">
The handle supplied in <i>ppAdditionalModesSet</i> was invalid.

</td>
</tr>
</table>

## Remarks

This function is available beginning with Windows 7.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_getadditionalmonitormodeset.md">DXGK_MONITOR_INTERFACE_V2::pfnGetAdditionalMonitorModeSet</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_monitor_interface_v2.md">DXGK_MONITOR_INTERFACE_V2</a>