---
UID: NC:video.PVIDEO_HW_LEGACYRESOURCES
title: PVIDEO_HW_LEGACYRESOURCES
author: windows-driver-content
description: HwVidLegacyResources returns a list of resources that are not listed in a device's PCI configuration space but that are decoded by the device.
old-location: display\hwvidlegacyresources.htm
old-project: display
ms.assetid: 015086e9-70b4-4756-9945-c9da17829e90
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: HwVidLegacyResources, HwVidLegacyResources callback function [Display Devices], PVIDEO_HW_LEGACYRESOURCES, VideoMiniport_Functions_a629bf4d-8f16-4d71-ab88-c691160a5df7.xml, display.hwvidlegacyresources, video/HwVidLegacyResources
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	HwVidLegacyResources
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---


# PVIDEO_HW_LEGACYRESOURCES callback function
<i>HwVidLegacyResources </i>returns a list of resources that are not listed in a device's PCI configuration space but that are decoded by the device.

## Syntax

```
PVIDEO_HW_LEGACYRESOURCES PvideoHwLegacyresources;

void PvideoHwLegacyresources(
  IN ULONG VendorId,
  IN ULONG DeviceId,
  IN OUT PVIDEO_ACCESS_RANGE *LegacyResourceList,
  IN OUT PULONG LegacyResourceCount
)
{...}
```

## Parameters

`VendorId`

Specifies a code that identifies the device's vendor. This is the vendor ID specified in the device's PCI configuration space. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/install/identifiers-for-pci-devices">Identifiers for PCI Devices</a>.

`DeviceId`

Specifies a code that identifies the particular device. This is the device ID specified in the device's PCI configuration space.

`*LegacyResourceList`

Pointer to an array of <a href="..\video\ns-video-_video_access_range.md">VIDEO_ACCESS_RANGE</a> structures. Each structure describes a device I/O port or memory range for the graphics adapter that is not listed in PCI configuration space.

`LegacyResourceCount`

Is the number of elements in the array to which <i>LegacyResourceList</i> points.


## Return Value

None

## Remarks

Legacy resources are those resources that are not listed in the device's PCI configuration space but that are decoded by the device. If the legacy resource list for the device is not known at compile time, a miniport driver should implement a <i>HwVidLegacyResources </i> function and initialize the <b>HwGetLegacyResources</b> member of <a href="..\video\ns-video-_video_hw_initialization_data.md">VIDEO_HW_INITIALIZATION_DATA</a> to point to this function. For example, a miniport driver that supports two devices with different sets of legacy resources would implement <i>HwVidLegacyResources </i> to report the legacy resources for a particular device at run time.

The resources returned by <i>HwVidLegacyResources </i> are added to the list of resources that PnP reserves for the device.

<i>HwVidLegacyResources</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |

## See Also

<a href="..\video\ns-video-_video_hw_initialization_data.md">VIDEO_HW_INITIALIZATION_DATA</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PVIDEO_HW_LEGACYRESOURCES callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>