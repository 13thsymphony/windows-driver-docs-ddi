---
UID: NS.D3DKMDDI._DXGKARG_RECOMMENDMONITORMODES
title: _DXGKARG_RECOMMENDMONITORMODES
author: windows-driver-content
description: The DXGKARG_RECOMMENDMONITORMODES structure contains arguments for the DxgkDdiRecommendMonitorModes function.
old-location: display\dxgkarg_recommendmonitormodes.htm
old-project: display
ms.assetid: 283f398e-4162-4c46-847b-834f8f303052
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGKARG_RECOMMENDMONITORMODES, DXGKARG_RECOMMENDMONITORMODES
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
req.alt-api: DXGKARG_RECOMMENDMONITORMODES
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
---

# _DXGKARG_RECOMMENDMONITORMODES structure



## -description
The DXGKARG_RECOMMENDMONITORMODES structure contains arguments for the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendmonitormodes.md">DxgkDdiRecommendMonitorModes</a> function. 



## -syntax

````
typedef struct _DXGKARG_RECOMMENDMONITORMODES {
  D3DDDI_VIDEO_PRESENT_TARGET_ID            VideoPresentTargetId;
  D3DKMDT_HMONITORSOURCEMODESET             hMonitorSourceModeSet;
  const DXGK_MONITORSOURCEMODESET_INTERFACE *pMonitorSourceModeSetInterface;
} DXGKARG_RECOMMENDMONITORMODES;
````


## -struct-fields

### -field VideoPresentTargetId

An integer that identifies a video present target on the display adapter.


### -field hMonitorSourceModeSet

A handle to a monitor source mode set object. This set contains a list of modes that are supported by the monitor that is connected to the video present target identified by <i>VideoPresentTargetId</i>.


### -field pMonitorSourceModeSetInterface

A pointer to a <a href="display.dxgk_monitorsourcemodeset_interface">DXGK_MONITORSOURCEMODESET_INTERFACE</a> structure. The structure contains pointers to functions that the display miniport driver can use to inspect, and possibly add modes to, the monitor source mode set.


## -remarks


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
<a href="display.dxgk_monitorsourcemodeset_interface">DXGK_MONITORSOURCEMODESET_INTERFACE</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_recommendmonitormodes.md">DxgkDdiRecommendMonitorModes</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_RECOMMENDMONITORMODES structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

