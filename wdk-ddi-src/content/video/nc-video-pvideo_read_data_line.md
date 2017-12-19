---
UID: NC.video.PVIDEO_READ_DATA_LINE
title: PVIDEO_READ_DATA_LINE
author: windows-driver-content
description: ReadDataLine reads a single data bit from the I2C serial data line.
old-location: display\readdataline.htm
old-project: display
ms.assetid: 071000a3-c1b7-47fd-aec7-9e9f32edddf6
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _VHF_CONFIG, *PVHF_CONFIG, PVHF_CONFIG, VHF_CONFIG
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
req.alt-api: ReadDataLine
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
req.product: Windows 10 or later.
---

# PVIDEO_READ_DATA_LINE callback



## -description
<i>ReadDataLine</i> reads a single data bit from the I2C serial data line.



## -prototype

````
PVIDEO_READ_DATA_LINE ReadDataLine;

BOOLEAN ReadDataLine(
   PVOID HwDeviceExtension
)
{ ... }
````


## -parameters

### -param HwDeviceExtension 

Pointer to the miniport driver's per-adapter storage area. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543119">Device Extensions</a>.


## -returns
<i>ReadDataLine</i> returns 1 if the serial data line is high and 0 if the serial data line is low.


## -remarks
<i>ReadDataLine</i> should be made pageable.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

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
<a href="display.i2c_functions">I2C Functions</a>
</dt>
<dt>
<a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a>
</dt>
<dt>
<a href="..\video\nc-video-pvideo_read_clock_line.md">ReadClockLine</a>
</dt>
<dt>
<a href="display.videoportddcmonitorhelper">VideoPortDDCMonitorHelper</a>
</dt>
<dt>
<a href="..\video\nc-video-pvideo_write_clock_line.md">WriteClockLine</a>
</dt>
<dt>
<a href="..\video\nc-video-pvideo_write_data_line.md">WriteDataLine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PVIDEO_READ_DATA_LINE callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

