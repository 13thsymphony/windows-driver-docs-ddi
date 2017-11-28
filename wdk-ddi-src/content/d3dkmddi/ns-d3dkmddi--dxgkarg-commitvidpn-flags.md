---
UID: NS.d3dkmddi._DXGKARG_COMMITVIDPN_FLAGS
title: DXGKARG_COMMITVIDPN_FLAGS
author: windows-driver-content
description: The DXGKARG_COMMITVIDPN_FLAGS structure identifies details about a call to the DxgkDdiCommitVidPn function.
old-location: display\dxgkarg_commitvidpn_flags.htm
old-project: display
ms.assetid: 02fe4216-101e-4ba7-88df-029f8bba9c17
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DXGKARG_COMMITVIDPN_FLAGS, DXGKARG_COMMITVIDPN_FLAGS
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
req.alt-api: DXGKARG_COMMITVIDPN_FLAGS
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

# DXGKARG_COMMITVIDPN_FLAGS structure



## -description
<p>The DXGKARG_COMMITVIDPN_FLAGS structure identifies details about a call to the <a href="display.dxgkddicommitvidpn">DxgkDdiCommitVidPn</a> function.</p>


## -syntax

````
typedef struct _DXGKARG_COMMITVIDPN_FLAGS {
  UINT PathPowerTransition  :1;
  UINT PathPoweredOff  :1;
  UINT Reserved  :30;
} DXGKARG_COMMITVIDPN_FLAGS;
````


## -struct-fields
<dl>

### -field <b>PathPowerTransition</b>

<dd>
<p>A UINT value that specifies whether the Microsoft DirectX graphics kernel subsystem calls the <a href="display.dxgkddicommitvidpn">DxgkDdiCommitVidPn</a> function to power off a connected monitor.</p>
<p>If <b>PathPowerTransition</b> is set to <b>TRUE</b>, the display miniport driver can optimize this call for a power down (for example, the driver might disable vertical syncs). The driver must also be aware that it might still receive calls to its <a href="display.dxgkddipresent">DxgkDdiPresent</a> function on the affected source.</p>
<p>Setting this member is equivalent to setting the first bit of a 32-bit value (0x00000001).</p>
<p>For more information, see the following Remarks section.</p>
</dd>

### -field <b>PathPoweredOff</b>

<dd>
<p>A UINT value that specifies whether the DirectX graphics kernel subsystem calls <a href="display.dxgkddicommitvidpn">DxgkDdiCommitVidPn</a> to inform the driver that the user changed modes.</p>
<p>If <b>PathPoweredOff</b> is set to <b>TRUE</b>, the display miniport driver should expect present operations that are based on the new topology. The driver cannot perform any operations that would cause the topology path to be powered on again (for example, the driver cannot enable vertical syncs) because the monitor should now be powered off.</p>
<p>If <b>PathPoweredOff</b> is set to <b>FALSE</b>, the topology path is powered on. The display miniport driver should program hardware for present operations that are based on the former topology path, and the driver should commit hardware to support this topology path. Setting this member is equivalent to setting the second bit of a 32-bit value (0x00000002).</p>
<p>For more information, see the following Remarks section.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the remaining 30 bits (0xFFFFFFFC) of a 32-bit value to zeros.</p>
</dd>
</dl>

## -remarks
<p>The DXGKARG_COMMITVIDPN_FLAGS structure stores information that the display miniport driver can use to determine how to respond to requested mode changes. With this information, the driver can distinguish between mode changes that occur during regular activity because an application requested a mode change, changes that occur because of power transitions, and changes that occur while monitors are turned off.</p>

<p>During regular activity, when the <a href="display.dxgkddicommitvidpn">DxgkDdiCommitVidPn</a> function is called, both <b>PathPowerTransition</b> and <b>PathPoweredOff</b> members will be <b>FALSE</b> so that the driver should apply mode changes immediately. Such mode changes are usually performed as isolated events. Therefore, there is no need for the driver to track any state that is associated with the previous mode configuration.</p>

<p>If monitors are being turned off or turned on, <b>PathPowerTransition</b> will be <b>TRUE</b> to indicate a power transition. In this case, a common pattern is that the monitors will be turned off, and then at some later time, the original configuration will be restored. It can be a significant workload for the driver to reset the display configuration completely after a system shutdown. Additionally, , the driver must continue to complete <a href="display.dxgkddipresent">DxgkDdiPresent</a> operations while the monitors are turned off. However, the driver can reduce its workload when a call is made to <i>DxgkDdiCommitVidPn</i> by making sure that the involved monitors are powered off. When power is restored, the driver workload to restore the display configuration will thereby be reduced.</p>

<p>Because the monitor might not be physically connected (at system resume time, for example), the driver should not rely on Windows to make a later call to the <a href="display.dxgkddisetpowerstate">DxgkDdiSetPowerState</a> function to set the power state of the child device of the display adapter. However, Windows will still request that the CRTC is to be turned on. If the driver does not turn on vertical sync when it is requested to do so by the display mode manager (DMM), and if the user later reconnects the monitor, the monitor display might be blank.</p>

<p><i>DxgkDdiPresent</i> operations must still be honored by the driver while monitors are turned off. The driver might have to act upon a mode change triggered by an application, for example to perform modifications to the rendering pipeline to account for rotation changes. Settings of <b>PathPowerTransition</b> = <b>FALSE</b> and <b>PathPoweredOff</b> = <b>TRUE</b> inform the driver that such a mode change has occurred. In this case, the driver must not turn on the monitors, but instead it should reprogram the hardware, if it is necessary, to accommodate the mode change so that additional <i>DxgkDdiPresent</i> operations can be completed. When such a mode change has been performed, and monitors are later turned back on, it is unlikely that the mode that occurred before the power down will be restored.</p>

<p>If a system resume operation is triggered after monitors were turned off for a system suspend operation, the driver can receive a <i>DxgkDdiCommitVidPn</i> call with both <b>PathPowerTransition</b> = <b>FALSE</b> and <b>PathPoweredOff</b> = <b>FALSE</b> before a <i>DxgkDdiCommitVidPn</i> call is made with <b>PathPowerTransition</b> = <b>TRUE</b>. This situation should only occur with an empty topology and, in this case, the driver should not turn monitors back on because the power transition is not yet completed.</p>

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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557552">DXGKARG_COMMITVIDPN</a>
</dt>
<dt>
<a href="display.dxgkddipresent">DxgkDdiPresent</a>
</dt>
<dt>
<a href="display.dxgkddisetpowerstate">DxgkDdiSetPowerState</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_COMMITVIDPN_FLAGS structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
