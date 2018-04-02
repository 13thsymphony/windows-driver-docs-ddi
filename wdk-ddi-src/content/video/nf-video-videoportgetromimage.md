---
UID: NF:video.VideoPortGetRomImage
title: VideoPortGetRomImage function
author: windows-driver-content
description: Reads the device's read-only memory (ROM).
old-location: display\videoportgetromimage.htm
old-project: display
ms.assetid: e4930661-fb88-458b-9460-129ab057e0f4
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortGetRomImage, VideoPortGetRomImage function [Display Devices], VideoPort_Functions_070e50af-a33d-4dc5-9bd1-9f60367f49b2.xml, display.videoportgetromimage, video/VideoPortGetRomImage
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
-	VideoPortGetRomImage
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortGetRomImage function
Reads the device's read-only memory (ROM).

## Syntax

```
VIDEOPORT_API PVOID VideoPortGetRomImage(
  IN PVOID HwDeviceExtension,
  IN PVOID Unused1,
  IN ULONG Unused2,
  IN ULONG Length
);
```

## Parameters

`HwDeviceExtension`

A pointer to the miniport driver's device extension.

`Unused1`

Currently ignored by the video port driver; should be set to <b>NULL</b>.

`Unused2`

Currently ignored by the video port driver; should be set to zero.

`Length`

Either the number of bytes of ROM data that the video port driver should read and return, or zero.


## Return Value

<b>VideoPortGetRomImage</b> returns a pointer to a buffer containing the device's ROM (BIOS) data on success; otherwise, returns <b>NULL</b> to indicate either there was insufficient memory for the operation, or the device's ROM could not be accessed.

## Remarks

<b>VideoPortGetRomImage</b> does not read ROM using the legacy 0xC0000 mapping. It reads ROM that can be discovered using the ACPI_METHOD_DISPLAY_ROM method or the ROM base address register.

The ACPI_METHOD_DISPLAY_ROM alias, defined in Dispmprt.h, represents the method used to obtain the BIOS ROM image. This method is required when the ROM image is stored in a proprietary format such as the system BIOS ROM. This method is not necessary if the ROM image can be read through a standard PCI interface.

The video port driver allocates a buffer of <i>Length</i> bytes and fills it with data read from the device's ROM. The video port driver always reads <i>Length</i> bytes from the beginning of the device's ROM.

If a miniport driver calls <b>VideoPortGetRomImage</b> multiple times, the video port driver will free the buffer from a previous call before allocating and returning a buffer in the current call. Consequently, a miniport driver must only reference the pointer returned by this call to <b>VideoPortGetRomImage</b>.

The miniport driver can free the buffer allocated by the video port driver by calling <b>VideoPortGetRomImage</b> with a <i>Length</i> of zero.

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

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570360">VideoPortScanRom</a>