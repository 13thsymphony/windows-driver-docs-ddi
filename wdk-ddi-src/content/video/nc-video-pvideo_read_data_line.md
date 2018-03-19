---
UID: NC:video.PVIDEO_READ_DATA_LINE
title: PVIDEO_READ_DATA_LINE
author: windows-driver-content
description: ReadDataLine reads a single data bit from the I2C serial data line.
old-location: display\readdataline.htm
old-project: display
ms.assetid: 071000a3-c1b7-47fd-aec7-9e9f32edddf6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PVIDEO_READ_DATA_LINE, ReadDataLine, ReadDataLine callback function [Display Devices], VideoMiniport_Functions_6507a035-50bc-4a1e-92bf-f07e75cf023b.xml, display.readdataline, video/ReadDataLine
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
-	ReadDataLine
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---


# PVIDEO_READ_DATA_LINE callback function
<i>ReadDataLine</i> reads a single data bit from the I2C serial data line.

## Syntax

```
PVIDEO_READ_DATA_LINE PvideoReadDataLine;

BOOLEAN PvideoReadDataLine(
  PVOID HwDeviceExtension
)
{...}
```

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


## Return Value

<i>ReadDataLine</i> returns 1 if the serial data line is high and 0 if the serial data line is low.

## Remarks

<i>ReadDataLine</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |

## See Also

<a href="..\video\nc-video-pvideo_read_clock_line.md">ReadClockLine</a>



<a href="..\video\nf-video-videoportddcmonitorhelper.md">VideoPortDDCMonitorHelper</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567383">I2C Functions</a>



<a href="..\video\nc-video-pvideo_write_data_line.md">WriteDataLine</a>



<a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a>



<a href="..\video\nc-video-pvideo_write_clock_line.md">WriteClockLine</a>