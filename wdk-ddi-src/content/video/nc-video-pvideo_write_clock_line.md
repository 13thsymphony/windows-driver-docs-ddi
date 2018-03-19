---
UID: NC:video.PVIDEO_WRITE_CLOCK_LINE
title: PVIDEO_WRITE_CLOCK_LINE
author: windows-driver-content
description: WriteClockLine sets the I2C serial clock line to high or low.
old-location: display\writeclockline.htm
old-project: display
ms.assetid: 4dfd6223-420e-4087-b5bd-8277575321f7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PVIDEO_WRITE_CLOCK_LINE, VideoMiniport_Functions_7d36df35-ac09-4a82-af0c-47a733617d9a.xml, WriteClockLine, WriteClockLine callback function [Display Devices], display.writeclockline, video/WriteClockLine
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
-	WriteClockLine
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---


# PVIDEO_WRITE_CLOCK_LINE callback function
<i>WriteClockLine</i> sets the I2C serial clock line to high or low.

## Syntax

```
PVIDEO_WRITE_CLOCK_LINE PvideoWriteClockLine;

void PvideoWriteClockLine(
  PVOID HwDeviceExtension,
  UCHAR Data
)
{...}
```

## Parameters

`HwDeviceExtension`

Pointer to the video miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.

`Data`

Supplies a value that specifies whether to set the serial clock line to high or low. A value of 0 specifies that the clock line should be set to low, and a value of 1 specifies that the clock line should be set to high.


## Return Value

None

## Remarks

<i>WriteClockLine</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |

## See Also

<a href="..\video\nc-video-pvideo_read_clock_line.md">ReadClockLine</a>



<a href="..\video\nf-video-videoportddcmonitorhelper.md">VideoPortDDCMonitorHelper</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567383">I2C Functions</a>



<a href="..\video\nc-video-pvideo_read_data_line.md">ReadDataLine</a>



<a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a>



<a href="..\video\nc-video-pvideo_write_data_line.md">WriteDataLine</a>