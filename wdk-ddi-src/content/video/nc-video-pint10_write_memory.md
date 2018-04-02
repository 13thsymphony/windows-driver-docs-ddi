---
UID: NC:video.PINT10_WRITE_MEMORY
title: PINT10_WRITE_MEMORY
author: windows-driver-content
description: The Int10WriteMemory function writes the contents of an input buffer to memory in the context of another thread.
old-location: display\int10writememory.htm
old-project: display
ms.assetid: a1143ca4-9c39-4bd7-92e1-473bdb447eb5
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: Int10WriteMemory, Int10WriteMemory callback function [Display Devices], PINT10_WRITE_MEMORY, VideoPort_Functions_6a882de2-2147-4b15-b4d8-6a87c49fa3d9.xml, display.int10writememory, video/Int10WriteMemory
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
-	Int10WriteMemory
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---


# PINT10_WRITE_MEMORY callback function
The <i>Int10WriteMemory</i> function writes the contents of an input buffer to memory in the context of another thread.

## Syntax

```
PINT10_WRITE_MEMORY Pint10WriteMemory;

VP_STATUS Pint10WriteMemory(
  IN PVOID Context,
  IN USHORT Seg,
  IN USHORT Off,
  IN PVOID Buffer,
  IN ULONG Length
)
{...}
```

## Parameters

`Context`

Pointer to a video port driver-defined context for the interface. This should be the same as the value in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a> structure after <a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a> returns.

`Seg`

Specifies the segment address of the buffer to be written.

`Off`

Specifies the offset within the segment indicated by the <i>Seg</i> parameter.

`Buffer`

Pointer to the memory location that marks the beginning of the input buffer.

`Length`

Is the length, in bytes, of the input buffer specified by the <i>Buffer</i> parameter.


## Return Value

The <i>Int10WriteMemory</i> function returns NO_ERROR upon success. Otherwise it returns an appropriate error code.

## Remarks

The video port implements this function, which can be accessed through a pointer in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a>