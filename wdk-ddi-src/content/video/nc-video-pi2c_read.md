---
UID: NC:video.PI2C_READ
title: PI2C_READ
author: windows-driver-content
description: The I2CRead function reads data over the I2C channel.
old-location: display\i2cread.htm
old-project: display
ms.assetid: 1418ec29-be67-46af-b6db-0b534ecafb37
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: I2CRead, I2CRead callback function [Display Devices], PI2C_READ, VideoPort_Functions_cb73b3b1-1646-43ef-ac61-5a14c9a53b9b.xml, display.i2cread, video/I2CRead
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	video.h
api_name:
-	I2CRead
product:
- Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---


# PI2C_READ callback function
The <i>I2CRead</i> function reads data over the <a href="https://msdn.microsoft.com/5a140cc0-ecc5-46ff-be3f-3c92f0f67dca">I2C</a> channel.

## Syntax

```
PI2C_READ Pi2cRead;

BOOLEAN Pi2cRead(
  IN PVOID HwDeviceExtension,
  IN PI2C_CALLBACKS I2CCallbacks,
  OUT PUCHAR Buffer,
  IN ULONG Length
)
{...}
```

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's per-adapter device extension.

`I2CCallbacks`

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff567382">I2C_CALLBACKS</a> structure, containing pointers to miniport driver-defined functions that read and write data and clock lines.

`Buffer`

Pointer to the data to be read.

`Length`

Specifies the number of bytes to be read.


## Return Value

<i>I2CRead</i> returns <b>TRUE</b> if the data was successfully read, and <b>FALSE</b> otherwise.

## Remarks

The video port implements this function, which can be accessed through a pointer in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570538">VIDEO_PORT_I2C_INTERFACE</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570538">VIDEO_PORT_I2C_INTERFACE</a>