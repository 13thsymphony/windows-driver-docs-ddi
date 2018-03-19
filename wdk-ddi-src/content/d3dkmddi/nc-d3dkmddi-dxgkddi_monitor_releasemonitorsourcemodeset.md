---
UID: NC:d3dkmddi.DXGKDDI_MONITOR_RELEASEMONITORSOURCEMODESET
title: DXGKDDI_MONITOR_RELEASEMONITORSOURCEMODESET
author: windows-driver-content
description: The pfnReleaseMonitorSourceModeSet function releases a handle to a monitor source mode set object.
old-location: display\dxgk_monitor_interface_pfnreleasemonitorsourcemodeset.htm
old-project: display
ms.assetid: af5f4a1b-232c-4192-96b4-8fa31dfe3019
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_MONITOR_RELEASEMONITORSOURCEMODESET, VidPnFunctions_5f8e1fd8-b807-4da2-901e-0284e21d858e.xml, d3dkmddi/pfnReleaseMonitorSourceModeSet, display.dxgk_monitor_interface_pfnreleasemonitorsourcemodeset, pfnReleaseMonitorSourceModeSet, pfnReleaseMonitorSourceModeSet callback function [Display Devices]
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
-	pfnReleaseMonitorSourceModeSet
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_MONITOR_RELEASEMONITORSOURCEMODESET callback function
The <b>pfnReleaseMonitorSourceModeSet</b> function releases a handle to a monitor source mode set object.

## Syntax

```
DXGKDDI_MONITOR_RELEASEMONITORSOURCEMODESET DxgkddiMonitorReleasemonitorsourcemodeset;

NTSTATUS DxgkddiMonitorReleasemonitorsourcemodeset(
  IN_CONST_D3DKMDT_ADAPTER hAdapter,
  IN_CONST_D3DKMDT_HMONITORSOURCEMODESET hMonitorSourceModeSet
)
{...}
```

## Parameters

`hAdapter`

[in] A handle that identifies a display adapter. The Microsoft DirectX graphics kernel subsystem previously provided this handle to the display miniport driver in the <i>DxgkInterface</i> parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_start_device.md">DxgkDdiStartDevice</a> function.

`hMonitorSourceModeSet`

[in] The handle to be released.


## Return Value

The <b>pfnReleaseMonitorSourceModeSet</b> function returns one of the following values.

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
The handle supplied in <i>hMonitorSourceModeSet</i> was invalid.

</td>
</tr>
</table>
 

This function might also return other error codes that are defined in <i>Ntstatus.h</i>.

## Remarks

When you have finished using a handle that you obtained by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset.md">pfnAcquireMonitorSourceModeSet</a>, you must release the handle by calling <b>pfnReleaseMonitorSourceModeSet</b>.

This function is also available in the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_monitor_interface_v2.md">DXGK_MONITOR_INTERFACE_V2</a> interface beginning with Windows 7.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_monitor_interface_v2.md">DXGK_MONITOR_INTERFACE_V2</a>