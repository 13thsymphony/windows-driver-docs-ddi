---
UID: NF.video.VideoPortGetRomImage
title: VideoPortGetRomImage function
author: windows-driver-content
description: Reads the device's read-only memory (ROM).
old-location: display\videoportgetromimage.htm
old-project: display
ms.assetid: e4930661-fb88-458b-9460-129ab057e0f4
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: VideoPortGetRomImage
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
req.alt-api: VideoPortGetRomImage
req.alt-loc: Videoprt.sys
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
req.product: Windows 10 or later.
---

# VideoPortGetRomImage function



## -description
Reads the device's read-only memory (ROM).


## -syntax

````
PVOID VideoPortGetRomImage(
  _In_       PVOID HwDeviceExtension,
  _Reserved_ PVOID Unused1,
  _Reserved_ ULONG Unused2,
  _In_       ULONG Length
);
````


## -parameters

### -param HwDeviceExtension [in]

A pointer to the miniport driver's device extension.

### -param Unused1 [in]

Currently ignored by the video port driver; should be set to <b>NULL</b>.

### -param Unused2 [in]

Currently ignored by the video port driver; should be set to zero.

### -param Length [in]

Either the number of bytes of ROM data that the video port driver should read and return, or zero.

## -returns
<b>VideoPortGetRomImage</b> returns a pointer to a buffer containing the device's ROM (BIOS) data on success; otherwise, returns <b>NULL</b> to indicate either there was insufficient memory for the operation, or the device's ROM could not be accessed.

## -remarks
<b>VideoPortGetRomImage</b> does not read ROM using the legacy 0xC0000 mapping. It reads ROM that can be discovered using the ACPI_METHOD_DISPLAY_ROM method or the ROM base address register.

The ACPI_METHOD_DISPLAY_ROM alias, defined in Dispmprt.h, represents the method used to obtain the BIOS ROM image. This method is required when the ROM image is stored in a proprietary format such as the system BIOS ROM. This method is not necessary if the ROM image can be read through a standard PCI interface.

The video port driver allocates a buffer of <i>Length</i> bytes and fills it with data read from the device's ROM. The video port driver always reads <i>Length</i> bytes from the beginning of the device's ROM.

If a miniport driver calls <b>VideoPortGetRomImage</b> multiple times, the video port driver will free the buffer from a previous call before allocating and returning a buffer in the current call. Consequently, a miniport driver must only reference the pointer returned by this call to <b>VideoPortGetRomImage</b>.

The miniport driver can free the buffer allocated by the video port driver by calling <b>VideoPortGetRomImage</b> with a <i>Length</i> of zero. 

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
Version
</th>
<td width="70%">
Available in Windows 2000 and later versions of the Windows operating systems.
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
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Videoprt.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>Videoprt.sys</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.videoportscanrom">VideoPortScanRom</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortGetRomImage function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
