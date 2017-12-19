---
UID: NS.D3DKMDT._D3DKMDT_MONITOR_SOURCE_MODE
title: _D3DKMDT_MONITOR_SOURCE_MODE
author: windows-driver-content
description: The D3DKMDT_MONITOR_SOURCE_MODE structure contains information about a monitor source mode.
old-location: display\d3dkmdt_monitor_source_mode.htm
old-project: display
ms.assetid: bccacf88-b66b-4d55-b3a8-9d9b8cfcede8
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMDT_MONITOR_SOURCE_MODE, D3DKMDT_MONITOR_SOURCE_MODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_MONITOR_SOURCE_MODE
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
req.irql: 
---

# _D3DKMDT_MONITOR_SOURCE_MODE structure



## -description
The D3DKMDT_MONITOR_SOURCE_MODE structure contains information about a monitor source mode.



## -syntax

````
typedef struct _D3DKMDT_MONITOR_SOURCE_MODE {
  D3DKMDT_MONITOR_SOURCE_MODE_ID      Id;
  D3DKMDT_VIDEO_SIGNAL_INFO           VideoSignalInfo;
  D3DKMDT_COLOR_BASIS                 ColorBasis;
  D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES  ColorCoeffDynamicRanges;
  D3DKMDT_MONITOR_CAPABILITIES_ORIGIN Origin;
  D3DKMDT_MODE_PREFERENCE             Preference;
} D3DKMDT_MONITOR_SOURCE_MODE;
````


## -struct-fields

### -field Id

An integer that identifies the monitor source mode.


### -field VideoSignalInfo

A <a href="display.d3dkmdt_video_signal_info">D3DKMDT_VIDEO_SIGNAL_INFO</a> enumerator that indicates the video mode standard (if any) that defines the mode.


### -field ColorBasis

A <a href="display.d3dkmdt_color_basis">D3DKMDT_COLOR_BASIS</a> enumerator that indicates the color basis of the mode.


### -field ColorCoeffDynamicRanges

A <a href="display.d3dkmdt_color_coeff_dynamic_ranges">D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES</a> structure that contains the dynamic ranges for the color channels in the mode's color basis.


### -field Origin

A value from the <a href="display.d3dkmdt_monitor_capabilities_origin">D3DKMDT_MONITOR_CAPABILITIES_ORIGIN</a> enumeration that indicates the source of the mode information. For example the mode information could be from a default monitor profile or it could be from an override in an INF file.


### -field Preference

A value from the <a href="display.d3dkmdt_mode_preference">D3DKMDT_MODE_PREFERENCE</a> enumeration that indicates whether the mode is the preferred mode in a <a href="display.monitor_source_mode_set_interface">monitor source mode set</a>.


## -remarks
The D3DKMDT_MONITOR_SOURCE_MODE_ID data type is defined in <i>D3dkmdt.h</i>.


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
<a href="display.d3dkmdt_vidpn_source_mode">D3DKMDT_VIDPN_SOURCE_MODE</a>
</dt>
<dt>
<a href="display.d3dkmdt_vidpn_target_mode">D3DKMDT_VIDPN_TARGET_MODE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_MONITOR_SOURCE_MODE structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

