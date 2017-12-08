---
UID: NE.d3dkmdt._D3DKMDT_MONITOR_CAPABILITIES_ORIGIN
title: _D3DKMDT_MONITOR_CAPABILITIES_ORIGIN
author: windows-driver-content
description: The D3DKMDT_MONITOR_CAPABILITIES_ORIGIN enumeration is used to indicate where a monitor's capability information was obtained.
old-location: display\d3dkmdt_monitor_capabilities_origin.htm
old-project: display
ms.assetid: fbbea7d7-2bd7-4dd0-bcb8-3fc93c7474a3
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DKMDT_MONITOR_CAPABILITIES_ORIGIN, D3DKMDT_MONITOR_CAPABILITIES_ORIGIN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_MONITOR_CAPABILITIES_ORIGIN
req.alt-loc: d3dkmdt.h
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
---

# _D3DKMDT_MONITOR_CAPABILITIES_ORIGIN enumeration



## -description
The D3DKMDT_MONITOR_CAPABILITIES_ORIGIN enumeration is used to indicate where a monitor's capability information was obtained.


## -syntax

````
typedef enum _D3DKMDT_MONITOR_CAPABILITIES_ORIGIN { 
  D3DKMDT_MCO_UNINITIALIZED                       = 0,
  D3DKMDT_MCO_DEFAULTMONITORPROFILE               = 1,
  D3DKMDT_MCO_MONITORDESCRIPTOR                   = 2,
  D3DKMDT_MCO_MONITORDESCRIPTOR_REGISTRYOVERRIDE  = 3,
  D3DKMDT_MCO_SPECIFICCAP_REGISTRYOVERRIDE        = 4,
  D3DKMDT_MCO_DRIVER                              = 5
} D3DKMDT_MONITOR_CAPABILITIES_ORIGIN;
````


## -enum-fields

### -field D3DKMDT_MCO_UNINITIALIZED

Indicates that a variable of type D3DKMDT_MONITOR_CAPABILITIES_ORIGIN has not yet been assigned a meaningful value.

### -field D3DKMDT_MCO_DEFAULTMONITORPROFILE

Indicates that the capability information was obtained from the default monitor profile.

### -field D3DKMDT_MCO_MONITORDESCRIPTOR

Indicates that the capability information was obtained from an Extended Display Information Data (EDID) descriptor.

### -field D3DKMDT_MCO_MONITORDESCRIPTOR_REGISTRYOVERRIDE

Indicates that the capability information was obtained from an INF file section that overrides the monitor's EDID descriptor.

### -field D3DKMDT_MCO_SPECIFICCAP_REGISTRYOVERRIDE

Indicates that the capability information was obtained from an INF file section that overrides a single capability.

### -field D3DKMDT_MCO_DRIVER

Indicates that the capability information was obtained by a call to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendmonitormodes.md">DxgkDdiRecommendMonitorModes</a> function.

## -remarks
The <b>Origin</b> member of the <a href="display.d3dkmdt_monitor_source_mode">D3DKMDT_MONITOR_SOURCE_MODE</a> structure is a constant from the D3DKMDT_MONITOR_CAPABILITIES_ORIGIN enumeration.

## -requirements
<table>
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
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.monitor_source_mode_set_interface">Monitor Source Mode Set Interface</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_MONITOR_CAPABILITIES_ORIGIN enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
