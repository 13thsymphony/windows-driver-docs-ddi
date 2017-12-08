---
UID: NS.d3dkmddi._DXGKARG_COMMITVIDPN
title: DXGKARG_COMMITVIDPN
author: windows-driver-content
description: The DXGKARG_COMMITVIDPN structure holds arguments for the DxgkDdiCommitVidPn function. The DxgkDdiCommitVidPn function makes a specified video present network (VidPN) active on a display adapter.
old-location: display\dxgkarg_commitvidpn.htm
old-project: display
ms.assetid: d297d917-fc49-454a-aacd-4db0ac7a09c2
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGKARG_COMMITVIDPN, DXGKARG_COMMITVIDPN
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
req.alt-api: DXGKARG_COMMITVIDPN
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
req.iface: 
---

# DXGKARG_COMMITVIDPN structure



## -description
<p>The DXGKARG_COMMITVIDPN structure holds arguments for the <a href="display.dxgkddicommitvidpn">DxgkDdiCommitVidPn</a> function. The <i>DxgkDdiCommitVidPn</i> function makes a specified video present network (VidPN) active on a display adapter.</p>


## -syntax

````
typedef struct _DXGKARG_COMMITVIDPN {
  D3DKMDT_HVIDPN                      hFunctionalVidPn;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID      AffectedVidPnSourceId;
  D3DKMDT_MONITOR_CONNECTIVITY_CHECKS MonitorConnectivityChecks;
  HANDLE                              hPrimaryAllocation;
  DXGKARG_COMMITVIDPN_FLAGS           Flags;
} DXGKARG_COMMITVIDPN;
````


## -struct-fields
<dl>

### -field hFunctionalVidPn

<dd>
<p>A handle to a functional VidPN object that is to be made active on the display adapter.</p>
</dd>

### -field AffectedVidPnSourceId

<dd>
<p>The constant D3DDDI_ID_ALL or the identifier of a particular video present source in the VidPN. If this member is a source identifier, <i>DxgkDdiCommitVidPn</i> updates only the modes of the video present paths that originate at that source -- <i>DxgkDdiCommitVidPn</i> does not have to inspect paths that originate from other sources, because those paths are the same in the new VidPN as they are in the currently active VidPN.  If this member is equal to D3DDDI_ID_ALL, <i>DxgkDdiCommitVidPn</i> must inspect and update the entire VidPN as a single transaction; that is, the entire new VidPN must be made active or the entire current VidPN must remain active.</p>
</dd>

### -field MonitorConnectivityChecks

<dd>
<p>A <a href="..\d3dkmdt\ne-d3dkmdt--d3dkmdt-monitor-connectivity-checks.md">D3DKMDT_MONITOR_CONNECTIVITY_CHECKS</a> enumerator (<b>D3DKMDT_MCC_IGNORE</b> or <b>D3DKMDT_MCC_ENFORCE</b>) that specifies whether to verify that video outputs in the new topology have monitors connected. If this member is equal to <b>D3DKMDT_MCC_ENFORCE</b> and one of the video outputs in the new VidPN's topology does not have a monitor connected, <i>DxgkDdiCommitVidPn</i> must leave the currently active VidPN in place and return STATUS_GRAPHICS_INVALID_VIDPN_TOPOLOGY. If this member is equal to D3DKMDT_MCC_IGNORE, <i>DxgkDdiCommitVidPn</i> can make the new VidPN active without checking to see whether any video outputs have monitors connected.</p>
</dd>

### -field hPrimaryAllocation

<dd>
<p>A handle to the primary allocation associated with the video present source identified by <i>AffectedVidPnSourceId</i>.</p>
</dd>

### -field Flags

<dd>
<p>[in] A <a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-commitvidpn-flags.md">DXGKARG_COMMITVIDPN_FLAGS</a> structure that identifies details about a call to the <a href="display.dxgkddicommitvidpn">DxgkDdiCommitVidPn</a> function.</p>
</dd>
</dl>

## -remarks
<p>The D3DDDI_ID_ALL constant is defined in <i>D3dukmddi.h</i>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="display.dxgkddicommitvidpn">DxgkDdiCommitVidPn</a>
</dt>
<dt>
<a href="..\d3dkmdt\ne-d3dkmdt--d3dkmdt-monitor-connectivity-checks.md">D3DKMDT_MONITOR_CONNECTIVITY_CHECKS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_COMMITVIDPN structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
