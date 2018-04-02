---
UID: NF:video.VideoPortScanRom
title: VideoPortScanRom function
author: windows-driver-content
description: The VideoPortScanRom function is obsolete in Windows XP and later versions. It is supported only for backward compatibility. VideoPortScanRom performs a case-sensitive search for a specified string in ROM.
old-location: display\videoportscanrom.htm
old-project: display
ms.assetid: 7787237c-5afd-46f2-ac75-6c0b41d37352
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortScanRom, VideoPortScanRom function [Display Devices], VideoPort_Functions_7bcf750d-48d5-4b3b-911f-90efd1f0eed1.xml, display.videoportscanrom, video/VideoPortScanRom
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
-	VideoPortScanRom
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortScanRom function
The <b>VideoPortScanRom</b> function is <b>obsolete</b> in Windows XP and later versions. It is supported only for backward compatibility. 

<b>VideoPortScanRom</b> performs a case-sensitive search for a specified string in ROM.

## Syntax

```
VIDEOPORT_API BOOLEAN VideoPortScanRom(
  PVOID  HwDeviceExtension,
  PUCHAR RomBase,
  ULONG  RomLength,
  PUCHAR String
);
```

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`RomBase`

Specifies the base ROM address at which the search should start. The given <i>RomBase</i> must be in a mapped range returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>.

`RomLength`

Specifies the size in bytes of the mapped ROM to be searched.

`String`

Pointer to the driver-allocated string to search for.


## Return Value

If the string is found, <b>VideoPortScanRom</b> returns <b>TRUE</b>. Otherwise, it returns <b>FALSE</b>.

## Remarks

<b>VideoPortScanRom</b> cannot be called from a miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/bd41bbbf-4ec8-4e6c-8620-d8a9fe0b8bad">HwVidTimer</a> functions, or from <a href="https://msdn.microsoft.com/library/windows/hardware/ff570339">VideoPortQueueDpc</a>, or from a callback to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570372">VideoPortSynchronizeExecution</a>.

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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570310">VideoPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570317">VideoPortGetRomImage</a>