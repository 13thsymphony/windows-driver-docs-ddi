---
UID: NS:iddcx.IDDCX_FRAME_STATISTICS
title: IDDCX_FRAME_STATISTICS
author: windows-driver-content
description: Gives information about the current frame being processed.
old-location: display\iddcx_frame_statistics.htm
old-project: display
ms.assetid: 5099ff37-eed9-44fd-8254-3828b8c5d8bd
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IDDCX_FRAME_STATISTICS, IDDCX_FRAME_STATISTICS structure [Display Devices], display.iddcx_frame_statistics, iddcx/IDDCX_FRAME_STATISTICS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iddcx.h
req.include-header: 
req.target-type: Windows
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
-	HeaderDef
api_location:
-	iddcx.h
api_name:
-	IDDCX_FRAME_STATISTICS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IDDCX_FRAME_STATISTICS structure
Gives information about the current frame being processed.

## Syntax
```
struct IDDCX_FRAME_STATISTICS {
  UINT                         Size;
  UINT                         PresentationFrameNumber;
  IDDCX_FRAME_STATUS           FrameStatus;
  UINT                         ReEncodeNumber;
  UINT                         FrameSliceTotal;
  UINT                         CurrentSlice;
  UINT64                       FrameAcquireQpcTime;
  UINT                         FrameProcessingStepsCount;
  IDDCX_FRAME_STATISTICS_STEP  *pFrameProcessingStep;
  UINT64                       SendStartQpcTime;
  UINT64                       SendStopQpcTime;
  UINT64                       SendCompleteQpcTime;
  IDDCX_FRAME_STATISTICS_FLAGS Flags;
  UINT                         ProcessedPixelCount;
  UINT                         FrameSizeInBytes;
};
```

## Members


`Size`

Total size of the structure

`PresentationFrameNumber`

The frame number provided in the ReleaseAndAcquireBuffer call

`FrameStatus`

Indicates the overall status of processing this frame

`ReEncodeNumber`

Zero based number to indicate the number of times the same frame has been encoded and sent. Re-encodes can be the result of the OS providing the same frame and frame number to the driver to encode or the driver having to re-encode outside of the normal OS presentation to satisfy the protocol.

`FrameSliceTotal`

Indicates the number of slices the driver processes the frame in. If slices are not used, then this should be set to the value one

`CurrentSlice`

Indicates the zero based slice number being reported. If slicing is not supported, then the driver should always set this to the value zero

`FrameAcquireQpcTime`

System Qpc time the driver acquired the buffer from the OS

`FrameProcessingStepsCount`

The size of the frame step array pointed to by pFrameParts

`pFrameProcessingStep`

Array of frame processing steps the driver performed

`SendStartQpcTime`

Marks the time when the driver started transmission for this slice to the device

<div class="alert"><b>Note</b>  NOTE : This marks the time the driver started calling the transmit API's, not when the data actually starts being transmitted</div>
<div> </div>

`SendStopQpcTime`

Marks the time when the driver started transmission for this slice to the device

<div class="alert"><b>Note</b>  This marks the time the driver started calling the transmit API's, not when the data actually starts being transmitted</div>
<div> </div>

`SendCompleteQpcTime`

Marks the time when the send was reported as complete by the OS. This is an optional time stamp that can be used if the driver uses asynchronous transmit API and a completion routine. In the event the driver does not have an asynchronous completion routine, this value should be set to zero

`Flags`

Frame statistic flags

`ProcessedPixelCount`

The total number of pixels processed in this frame

`FrameSizeInBytes`

Total size of the data send to device for this frame, this includes all the slices


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | iddcx.h |