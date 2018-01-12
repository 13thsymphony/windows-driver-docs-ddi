---
UID: NS:d3dkmddi._DXGK_MONITOR_INTERFACE
title: _DXGK_MONITOR_INTERFACE
author: windows-driver-content
description: The DXGK_MONITOR_INTERFACE structure contains pointers to functions that belong to the Monitor Interface, which is implemented by the video present network (VidPN) manager.
old-location: display\dxgk_monitor_interface.htm
old-project: display
ms.assetid: edb6df63-7354-4da3-b641-2ce7f28ca7e8
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_MONITOR_INTERFACE, DXGK_MONITOR_INTERFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_MONITOR_INTERFACE
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
req.irql: PASSIVE_LEVEL
req.typenames: DXGK_MONITOR_INTERFACE
---

# _DXGK_MONITOR_INTERFACE structure



## -description
The DXGK_MONITOR_INTERFACE structure contains pointers to functions that belong to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568433">Monitor Interface</a>, which is implemented by the video present network (VidPN) manager.



## -syntax

````
typedef struct _DXGK_MONITOR_INTERFACE {
  DXGK_MONITOR_INTERFACE_VERSION              Version;
  DXGKDDI_MONITOR_ACQUIREMONITORSOURCEMODESET pfnAcquireMonitorSourceModeSet;
  DXGKDDI_MONITOR_RELEASEMONITORSOURCEMODESET pfnReleaseMonitorSourceModeSet;
  DXGKDDI_MONITOR_GETMONITORFREQUENCYRANGESET pfnGetMonitorFrequencyRangeSet;
  DXGKDDI_MONITOR_GETMONITORDESCRIPTORSET     pfnGetMonitorDescriptorSet;
} DXGK_MONITOR_INTERFACE;
````


## -struct-fields

### -field Version

A value from the <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_monitor_interface_version.md">DXGK_MONITOR_INTERFACE_VERSION</a> enumeration that indicates the monitor interface version. Must be set to 1.


### -field pfnAcquireMonitorSourceModeSet

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_acquiremonitorsourcemodeset.md">pfnAcquireMonitorSourceModeSet</a> function.


### -field pfnReleaseMonitorSourceModeSet

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_releasemonitorsourcemodeset.md">pfnReleaseMonitorSourceModeSet</a> function.


### -field pfnGetMonitorFrequencyRangeSet

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_getmonitorfrequencyrangeset.md">pfnGetMonitorFrequencyRangeSet</a> function.


### -field pfnGetMonitorDescriptorSet

A pointer to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_monitor_getmonitordescriptorset.md">pfnGetMonitorDescriptorSet</a> function.


## -remarks
<p class="note">this structure.


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
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_monitor_interface_v2.md">DXGK_MONITOR_INTERFACE_V2</a>
</dt>
<dt>
<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_monitor_interface_version.md">DXGK_MONITOR_INTERFACE_VERSION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_MONITOR_INTERFACE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

