---
UID: NC:video.PVIDEO_WRITE_DATA_LINE
title: PVIDEO_WRITE_DATA_LINE
author: windows-driver-content
description: WriteDataLine sets the I2C serial data line to high or low.
old-location: display\writedataline.htm
old-project: display
ms.assetid: 3f860619-a479-4291-b3f3-ea4d309beee7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PVIDEO_WRITE_DATA_LINE, VideoMiniport_Functions_35effeac-fbe1-44b9-905f-111460800d86.xml, WriteDataLine, WriteDataLine callback function [Display Devices], display.writedataline, video/WriteDataLine
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
-	WriteDataLine
product:
- Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---


# PVIDEO_WRITE_DATA_LINE callback function
<i>WriteDataLine</i> sets the I2C serial data line to high or low.

## Syntax

```
PVIDEO_WRITE_DATA_LINE PvideoWriteDataLine;

void PvideoWriteDataLine(
  PVOID HwDeviceExtension,
  UCHAR Data
)
{...}
```

## Parameters

`HwDeviceExtension`

Pointer to the video miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.

`Data`

Supplies a value that specifies whether to set the serial data line to high or low. A value of 0 specifies that the data line should be set to low, and a value of 1 specifies that the data line should be set to high.


## Return Value

None

## Remarks

<i>WriteDataLine</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |

## See Also

<a href="https://msdn.microsoft.com/175030c1-95d9-4a3b-976c-16e04852cb91">HwVidGetVideoChildDescriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567383">I2C Functions</a>



<a href="https://msdn.microsoft.com/1051a234-ef63-454e-8957-292e86f4efcd">ReadClockLine</a>



<a href="https://msdn.microsoft.com/071000a3-c1b7-47fd-aec7-9e9f32edddf6">ReadDataLine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570290">VideoPortDDCMonitorHelper</a>



<a href="https://msdn.microsoft.com/4dfd6223-420e-4087-b5bd-8277575321f7">WriteClockLine</a>