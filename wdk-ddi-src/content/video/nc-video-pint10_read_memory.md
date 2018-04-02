---
UID: NC:video.PINT10_READ_MEMORY
title: PINT10_READ_MEMORY
author: windows-driver-content
description: The Int10ReadMemory function reads a block of memory in the context of another thread and stores it in an output buffer.
old-location: display\int10readmemory.htm
old-project: display
ms.assetid: 94b72ad0-1ace-4fde-a4a9-1078103e3d9b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: Int10ReadMemory, Int10ReadMemory callback function [Display Devices], PINT10_READ_MEMORY, VideoPort_Functions_fab5815b-1478-4d19-823f-05fd1de02b0c.xml, display.int10readmemory, video/Int10ReadMemory
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
-	Int10ReadMemory
product: Windows
targetos: Windows
req.typenames: VHF_CONFIG, *PVHF_CONFIG
req.product: Windows 10 or later.
---


# PINT10_READ_MEMORY callback function
The <i>Int10ReadMemory </i>function reads a block of memory in the context of another thread and stores it in an output buffer.

## Syntax

```
PINT10_READ_MEMORY Pint10ReadMemory;

VP_STATUS Pint10ReadMemory(
  IN PVOID Context,
  IN USHORT Seg,
  IN USHORT Off,
  OUT PVOID Buffer,
  IN ULONG Length
)
{...}
```

## Parameters

`Context`

Pointer to a video port driver-defined context for the interface. This should be the same as the value in the <b>Context</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570539">VIDEO_PORT_INT10_INTERFACE</a> structure after <a href="https://msdn.microsoft.com/library/windows/hardware/ff570337">VideoPortQueryServices</a> returns.

`Seg`

Specifies the segment address of the buffer to be read.

`Off`

Specifies the offset within the segment indicated by the <i>Seg</i> parameter.

`Buffer`

Pointer to a memory location that indicates the beginning of the output buffer.

`Length`

Is the length, in bytes, of the output buffer specified by the <i>Buffer</i> parameter.


## Return Value

The <i>Int10ReadMemory</i> function returns NO_ERROR upon success. Otherwise it returns an appropriate error code.

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