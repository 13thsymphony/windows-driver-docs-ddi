---
UID: NS.NTDDVDEO._VIDEO_POWER_MANAGEMENT
title: _VIDEO_POWER_MANAGEMENT
author: windows-driver-content
description: The VIDEO_POWER_MANAGEMENT structure contains information required by the miniport driver to perform power management.
old-location: display\video_power_management.htm
old-project: display
ms.assetid: 9522c504-9bdb-4388-b047-340a211463dd
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _VIDEO_POWER_MANAGEMENT, PVIDEO_POWER_MANAGEMENT, *PVIDEO_POWER_MANAGEMENT, VIDEO_POWER_MANAGEMENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VIDEO_POWER_MANAGEMENT
req.alt-loc: ntddvdeo.h
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

# _VIDEO_POWER_MANAGEMENT structure



## -description
The VIDEO_POWER_MANAGEMENT structure contains information required by the miniport driver to perform power management.



## -syntax

````
typedef struct _VIDEO_POWER_MANAGEMENT {
  ULONG Length;
  ULONG DPMSVersion;
  ULONG PowerState;
} VIDEO_POWER_MANAGEMENT, *PVIDEO_POWER_MANAGEMENT;
````


## -struct-fields

### -field Length

Is the size in bytes of this VIDEO_POWER_MANAGEMENT structure.


### -field DPMSVersion

Specifies the version of the Display Power Management Signaling (DPMS) standard supported by the device. Currently, the video port driver sets this member to zero, which corresponds with Version 1.0 of the <a href="wdkgloss.v#wdkgloss.video_electronics_standards_association__vesa_#wdkgloss.video_electronics_standards_association__vesa_"><i>VESA</i></a> DPMS Standard.


### -field PowerState

Specifies the power management state to be set or queried. This member can be one of the following values in the VIDEO_POWER_STATE enumeration:




### -field VideoPowerOn

The monitor and graphics adapter are both fully powered on and operational.


### -field VideoPowerStandBy

The monitor is running at a reduced power level that requires a short recovery time to <b>VideoPowerOn</b>. The graphics adapter is powered on (registers are still active and video memory is refreshed); however, clocks might be lost.


### -field VideoPowerSuspend

The monitor is running at a substantially reduced power level that requires a possibly longer recovery time than <b>VideoPowerStandBy</b> to <b>VideoPowerOn</b>. The graphics adapter is off.


### -field VideoPowerOff

The monitor and graphics adapter are both off, consuming no power at all.


### -field VideoPowerHibernate

The monitor and graphics adapter are both fully powered on and operational.

</dd>
</dl>

## -remarks
The video port driver allocates and fills in the VIDEO_POWER_MANAGEMENT structure. Depending on the power management request dispatched to the video port, the video port driver passes this structure to the miniport driver's <a href="..\video\nc-video-pvideo_hw_power_get.md">HwVidGetPowerState</a> or <a href="..\video\nc-video-pvideo_hw_power_set.md">HwVidSetPowerState</a> routine.

<b>VideoPowerHibernate</b> is provided to the miniport driver as notification only. The miniport driver's <i>HwVidSetPowerState</i> function must leave the monitor and graphics adapter fully powered on and operational. For all other states, the miniport driver must put the device into the specified power state.

A driver will always enter all other power states from the <b>VideoPowerOn</b> state. For example, a driver will not move directly to <b>VideoPowerHibernate</b> from <b>VideoPowerOff</b>; it will always go from <b>VideoPowerHibernate</b> to <b>VideoPowerOn</b> and then to <b>VideoPowerOff</b>.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddvdeo.h (include Ntddvdeo.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\video\nc-video-pvideo_hw_power_get.md">HwVidGetPowerState</a>
</dt>
<dt>
<a href="..\video\nc-video-pvideo_hw_power_set.md">HwVidSetPowerState</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_POWER_MANAGEMENT structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

