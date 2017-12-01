---
UID: NC.video.PVIDEO_HW_POWER_SET
title: PVIDEO_HW_POWER_SET
author: windows-driver-content
description: HwVidSetPowerState sets the power state of the specified device.
old-location: display\hwvidsetpowerstate.htm
old-project: display
ms.assetid: d7800ab6-9d8f-47a7-b919-8b6b0197d163
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: VHF_CONFIG, VHF_CONFIG, *PVHF_CONFIG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HwVidSetPowerState
req.alt-loc: video.h
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
req.iface: 
req.product: Windows 10 or later.
---

# PVIDEO_HW_POWER_SET callback



## -description
<p><i>HwVidSetPowerState</i> sets the power state of the specified device.</p>


## -prototype

````
PVIDEO_HW_POWER_SET HwVidSetPowerState;

VP_STATUS HwVidSetPowerState(
   PVOID                   HwDeviceExtension,
   ULONG                   HwId,
   PVIDEO_POWER_MANAGEMENT VideoPowerControl
)
{ ... }
````


## -parameters
<dl>

### -param <i>HwDeviceExtension</i> 

<dd>
<p>Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.</p>
</dd>

### -param <i>HwId</i> 

<dd>
<p>Pointer to a 32-bit <a href="wdkgloss.d#wdkgloss.device_id#wdkgloss.device_id"><i>device ID</i></a> that uniquely identifies the device for which the miniport driver should set the power state. This parameter is the value returned by the miniport driver's <a href="..\video\nc-video-pvideo-hw-get-child-descriptor.md">HwVidGetVideoChildDescriptor</a> function. A value of DISPLAY_ADAPTER_HW_ID indicates that the miniport driver should set the power state of the adapter itself.</p>
</dd>

### -param <i>VideoPowerControl</i> 

<dd>
<p>Pointer to a <a href="..\ntddvdeo\ns-ntddvdeo--video-power-management.md">VIDEO_POWER_MANAGEMENT</a> structure that specifies the power state to be set.</p>
</dd>
</dl>

## -returns
<p><i>HwVidSetPowerState</i> should always return NO_ERROR.</p>

## -remarks
<p><i>HwVidSetPowerState</i> is a required function in a video miniport driver.</p>

<p>The driver should check the ID specified in <i>HwId</i> to determine the device on which to set the power state. The driver should then set that device's power state to the level specified in the <b>PowerState</b> member of the VIDEO_POWER_MANAGEMENT structure to which <i>VideoPowerControl</i> points.</p>

<p><i>HwVidSetPowerState</i> should be made pageable.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\video\nc-video-pvideo-hw-get-child-descriptor.md">HwVidGetVideoChildDescriptor</a>
</dt>
<dt>
<a href="..\video\nc-video-pvideo-hw-power-get.md">HwVidGetPowerState</a>
</dt>
<dt>
<a href="..\ntddvdeo\ns-ntddvdeo--video-power-management.md">VIDEO_POWER_MANAGEMENT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PVIDEO_HW_POWER_SET callback function%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
