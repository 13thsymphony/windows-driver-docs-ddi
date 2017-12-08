---
UID: NC.d3dkmddi.DXGKDDI_RECOMMENDMONITORMODES
title: DXGKDDI_RECOMMENDMONITORMODES
author: windows-driver-content
description: The DxgkDdiRecommendMonitorModes function inspects the monitor source mode set that is associated with a particular video present target and possibly adds modes to the set.
old-location: display\dxgkddirecommendmonitormodes.htm
old-project: display
ms.assetid: 1fa29ab6-1faa-4be6-ae87-4cac9057471d
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
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
req.alt-api: DxgkDdiRecommendMonitorModes
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: < DISPATCH_LEVEL
---

# DXGKDDI_RECOMMENDMONITORMODES callback



## -description
The <i>DxgkDdiRecommendMonitorModes</i> function inspects the monitor source mode set that is associated with a particular video present target and possibly adds modes to the set.


## -prototype

````
DXGKDDI_RECOMMENDMONITORMODES DxgkDdiRecommendMonitorModes;

NTSTATUS APIENTRY DxgkDdiRecommendMonitorModes(
  _In_ const HANDLE                              hAdapter,
  _In_ const DXGKARG_RECOMMENDMONITORMODES CONST *pRecommendMonitorModesArg
)
{ ... }
````


## -parameters

### -param hAdapter [in]

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.

### -param pRecommendMonitorModesArg [in]

A pointer to a <a href="display.dxgkarg_recommendmonitormodes">DXGKARG_RECOMMENDMONITORMODES</a> structure that contains function arguments.

## -returns
<i>DxgkDdiRecommendMonitorModes</i> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The function succeeded.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl>The function failed because it was unable to allocate enough memory.

 

The miniport driver should pass through any error code that it gets from the operating system for which it does not have a fallback code path.

## -remarks
<i>DxgkDdiRecommendMonitorModes</i> should be made pageable.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt; DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.monitor_source_mode_set_interface">Monitor Source Mode Set Interface</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_RECOMMENDMONITORMODES callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
