---
UID: NC:video.PVIDEO_HW_POWER_GET
title: PVIDEO_HW_POWER_GET
author: windows-driver-content
description: HwVidGetPowerState queries whether the device can support the requested power state.
old-location: display\hwvidgetpowerstate.htm
old-project: display
ms.assetid: 747cfbfb-2a38-4a0d-b8c6-662d0c3967ba
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _USBSIDEBANDAUDIO_VOLUME_PARAMS, *PUSBSIDEBANDAUDIO_VOLUME_PARAMS, USBSIDEBANDAUDIO_VOLUME_PARAMS
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
req.alt-api: HwVidGetPowerState
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
req.typenames: *PUSBSIDEBANDAUDIO_VOLUME_PARAMS, USBSIDEBANDAUDIO_VOLUME_PARAMS
req.product: Windows 10 or later.
---

# PVIDEO_HW_POWER_GET callback



## -description
<i>HwVidGetPowerState</i> queries whether the device can support the requested power state.



## -prototype

````
PVIDEO_HW_POWER_GET HwVidGetPowerState;

VP_STATUS HwVidGetPowerState(
   PVOID                   HwDeviceExtension,
   ULONG                   HwId,
   PVIDEO_POWER_MANAGEMENT VideoPowerControl
)
{ ... }
````


## -parameters

### -param HwDeviceExtension 

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


### -param HwId 

Pointer to a 32-bit <a href="wdkgloss.d#wdkgloss.device_id#wdkgloss.device_id"><i>device ID</i></a> that uniquely identifies the device that the miniport driver should query. This parameter is returned by the miniport driver's <a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a> function. Alternatively, a value of DISPLAY_ADAPTER_HW_ID indicates that power information is being requested of the adapter itself.


### -param VideoPowerControl 

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570542">VIDEO_POWER_MANAGEMENT</a> structure that specifies the power state for which support is being queried.


## -returns
<i>HwVidGetPowerState</i> returns one of the following values:
<dl>
<dt><b>NO_ERROR </b></dt>
</dl>The device supports the requested power state.
<dl>
<dt><b>ERROR_DEVICE_REINITIALIZATION_NEEDED</b></dt>
</dl>The driver failed the power state query.

 


## -remarks
<i>HwVidGetPowerState</i> is a required function in a video miniport driver.

The driver should check the ID specified in <i>HwId</i> to determine which device to query. The driver should then determine whether that device supports the power state specified in the <b>PowerState</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570542">VIDEO_POWER_MANAGEMENT</a> structure to which <i>VideoPowerControl</i> points.

This function must not return the current power state of the device.

<i>HwVidGetPowerState</i> should be made pageable.


## -see-also
<dl>
<dt>
<a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a>
</dt>
<dt>
<a href="..\video\nc-video-pvideo_hw_power_set.md">HwVidSetPowerState</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570542">VIDEO_POWER_MANAGEMENT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PVIDEO_HW_POWER_GET callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

