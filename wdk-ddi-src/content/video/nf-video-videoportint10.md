---
UID: NF:video.VideoPortInt10
title: VideoPortInt10 function
author: windows-driver-content
description: The VideoPortInt10 function performs the equivalent of an MS-DOS INT10 operation, such as setting the video mode. VideoPortInt10 runs the BIOS ROM code on the device.
old-location: display\videoportint10.htm
old-project: display
ms.assetid: 5743d84c-6132-4058-b517-250b5de9a6b5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortInt10, VideoPortInt10 function [Display Devices], VideoPort_Functions_681fc4cc-f8f5-4d26-b3eb-8f4098339470.xml, display.videoportint10, video/VideoPortInt10
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortInt10
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortInt10 function
The <b>VideoPortInt10</b> function performs the equivalent of an MS-DOS INT10 operation, such as setting the video mode. <b>VideoPortInt10</b> runs the BIOS ROM code on the device.

## Syntax

```
VIDEOPORT_API VP_STATUS VideoPortInt10(
  PVOID                     HwDeviceExtension,
  PVIDEO_X86_BIOS_ARGUMENTS BiosArguments
);
```

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`BiosArguments`

Pointer to a structure containing values for the x86 registers that should be set before making the BIOS call. The miniport driver should set any unused registers to zero. All values set up in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570553">VIDEO_x86_BIOS_ARGUMENTS</a> structure are interpreted as immediate values.


## Return Value

<b>VideoPortInt10</b> returns NO_ERROR if it successfully called the given BIOS INT10 routine; otherwise, it returns an error status.

## Remarks

Generally, VGA-compatible miniport drivers, which support full-screen MS-DOS applications on x86-based machines, call <b>VideoPortInt10</b>. Such a driver's <a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a> function must have set up the <b>VdmPhysicalVideoMemoryAddress</b> and <b>VdmPhysicalVideoMemoryLength</b> for the range in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a> structure.

However, other video miniport drivers also can call this function.

Because <b>VideoPortInt10</b> interprets the <i>BiosArgument</i> parameter values as immediate values, the caller cannot pass in or retrieve data from a memory buffer with this function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/8c880eff-4b4c-439e-9239-f2343c1fe084">HwVidFindAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570531">VIDEO_PORT_CONFIG_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570553">VIDEO_x86_BIOS_ARGUMENTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>