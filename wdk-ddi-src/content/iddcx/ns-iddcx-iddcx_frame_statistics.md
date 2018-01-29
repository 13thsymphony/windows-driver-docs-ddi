---
UID : NS:iddcx.IDDCX_FRAME_STATISTICS
title : IDDCX_FRAME_STATISTICS
author : windows-driver-content
description : Gives information about the current frame being processed.
old-location : display\iddcx_frame_statistics.htm
old-project : display
ms.assetid : 5099ff37-eed9-44fd-8254-3828b8c5d8bd
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : IDDCX_FRAME_STATISTICS structure [Display Devices], iddcx/IDDCX_FRAME_STATISTICS, display.iddcx_frame_statistics, IDDCX_FRAME_STATISTICS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : iddcx.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : 
---

# IDDCX_FRAME_STATISTICS structure
Gives information about the current frame being processed.

## Syntax
````
typedef struct IDDCX_FRAME_STATISTICS {
  UINT                                                                 Size;
  UINT                                                                 PresentationFrameNumber;
  IDDCX_FRAME_STATUS                                                   FrameStatus;
  UINT                                                                 ReEncodeNumber;
  UINT                                                                 FrameSliceTotal;
  UINT                                                                 CurrentSlice;
  UINT64                                                               FrameAcquireQpcTime;
  UINT                                                                 FrameProcessingStepsCount;
  _Field_size_(FrameProcessingStepsCount) IDDCX_FRAME_STATISTICS_STEP* pFrameProcessingStep;
  UINT64                                                               SendStartQpcTime;
  UINT64                                                               SendStopQpcTime;
  UINT64                                                               SendCompleteQpcTime;
  IDDCX_FRAME_STATISTICS_FLAGS                                         Flags;
  UINT                                                                 ProcessedPixelCount;
  UINT                                                                 FrameSizeInBytes;
} IDDCX_FRAME_STATISTICS, *IDDCX_FRAME_STATISTICS;
````

## Members


`CurrentSlice`

Indicates the zero based slice number being reported. If slicing is not supported, then the driver should always set this to the value zero

`Flags`

Frame statistic flags

`FrameAcquireQpcTime`

System Qpc time the driver acquired the buffer from the OS

`FrameProcessingStepsCount`

The size of the frame step array pointed to by pFrameParts

`FrameSizeInBytes`

Total size of the data send to device for this frame, this includes all the slices

`FrameSliceTotal`

Indicates the number of slices the driver processes the frame in. If slices are not used, then this should be set to the value one

`FrameStatus`

Indicates the overall status of processing this frame

`pFrameProcessingStep`

Array of frame processing steps the driver performed

`PresentationFrameNumber`

The frame number provided in the ReleaseAndAcquireBuffer call

`ProcessedPixelCount`

The total number of pixels processed in this frame

`ReEncodeNumber`

Zero based number to indicate the number of times the same frame has been encoded and sent. Re-encodes can be the result of the OS providing the same frame and frame number to the driver to encode or the driver having to re-encode outside of the normal OS presentation to satisfy the protocol.

`SendCompleteQpcTime`

Marks the time when the send was reported as complete by the OS. This is an optional time stamp that can be used if the driver uses asynchronous transmit API and a completion routine. In the event the driver does not have an asynchronous completion routine, this value should be set to zero

`SendStartQpcTime`

Marks the time when the driver started transmission for this slice to the device
<div class="alert"><b>Note</b>  NOTE : This marks the time the driver started calling the transmit API's, not when the data actually starts being transmitted</div><div> </div>

`SendStopQpcTime`

Marks the time when the driver started transmission for this slice to the device
<div class="alert"><b>Note</b>  This marks the time the driver started calling the transmit API's, not when the data actually starts being transmitted</div><div> </div>

`Size`

Total size of the structure


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | iddcx.h |